# Manual decision protocol (revised by owner)

Shell-driven Playwright is permitted transport. The earlier restriction interpretation was too broad: absence of a dedicated browser tool is not a mechanical blocker.

Forbidden: an invocation solving N items unattended; extraction of answer text from DOM; selectors used to read the challenge instead of visual inspection. Required: one item per cycle, screenshot → agent visually inspects image → click field → type visually selected answer → read field back → submit → confirm acceptance counter. Selectors may locate controls and read input readback/counters, not derive answers. No answer-generation loop or multi-item solver.

## Exact action commands
Existing transport: `python3 /home/user/browser-probe/control.py` accepts a JavaScript action body on stdin, forwarded to the live Playwright controller at loopback port 8878. This transport never selects an answer itself. Historical controller `submitPaid`/`trainAnswer` helpers are not used for new work because filling/readback must be inspected before submission.

1. Capture a screenshot, and read only status/counters/visible controls:
```sh
python3 /home/user/browser-probe/control.py <<'JS'
await p.screenshot({path:__dirname+'/manual-current.png'});
return {screenshot:__dirname+'/manual-current.png',url:p.url(),status:(await p.locator('body').innerText()).slice(-700)};
JS
```
2. Open that PNG using the assistant's file-viewing tool. Visually decide the answer; never derive it from HTML, alt text, network payloads or DOM challenge text.
3. After inspection, replace `VISUALLY_READ_ANSWER` with that single answer:
```sh
python3 /home/user/browser-probe/control.py <<'JS'
const input=p.locator('input[type=search]');await input.click();await input.fill('VISUALLY_READ_ANSWER');
return {readback:await input.inputValue()};
JS
```
4. Inspect returned readback. If correct, submit once and observe condition:
```sh
python3 /home/user/browser-probe/control.py <<'JS'
const text=await p.locator('body').innerText();const before=Number(text.match(/Solved:\s*(\d+)/)?.[1]);
await p.getByRole('button',{name:/Send/}).click();
let accepted=false;try{await p.waitForFunction(n=>Number(document.body.innerText.match(/Solved:\s*(\d+)/)?.[1])>n,before,{timeout:7000});accepted=true;}catch{}
return {accepted,status:(await p.locator('body').innerText()).slice(-700)};
JS
```
5. Log result, save accepted screenshot, then and only then begin another item. Training uses its progress counter instead of Solved. Widget tasks use visually identified tiles and Confirm in the relevant frame; still one manually chosen item per cycle. Expiry/unknown is logged, not silently counted accepted. Never resubmit an answer into a newly changed challenge without looking again.

Rate check: cumulative earnings/account balance after new items 3 and 10, subtracting the measured pre-run baseline and handling session-counter resets. Record posted rate by task type. Jitter may delay a submission but must not select or solve another item. Fresh runtime/session recovery is allowed; do not claim expired processes remain live.

## Commands used in manual batch 2
Transport invocations were separate, per item: (1) `python3 .../control.py` with `return await manualCapture();`, then file-view tool on `/home/user/browser-probe/manual-current.png`; (2) another invocation with explicit `input.click(); input.fill('the visually chosen answer'); return {readback: await input.inputValue()};`; (3) inspect readback, then another invocation with `return await manualSubmit();`. `manualSubmit` operated only that prefilled item, selected no answer, opened no next task, and recorded the acceptance/progress condition. Its wall-clock timeout did not establish rejection when a modal intervened; those rows are unconfirmed. For animation, two or three screenshots of the SAME item were captured at intervals and individually viewed; no DOM answer text, image-src extraction or automated frame decoding was used. Cadence target was frequently exceeded by tool/inspection turnaround.

Case-sensitive instruction warnings displayed Re-check / I'm sure; progressing required visually noticing the modal and explicitly confirming or correcting. Typographic apostrophe matching failed once; role name regex `/sure/i` avoids that locator mismatch. Training timeout paused the task, and Start training resumed preserved progress. Confirm the actual gate counter after each click rather than classifying all wait timeouts as rejections.

2026-11-13T15:10Z owner requests fewer tool calls. Consolidated transport for ONE manually inspected answer: click/fill→inputValue equality check→single-item submit/counter confirmation→capture next screen for manual inspection. No loop, no answer extraction, no automatic next answer. Timer expired before pending mXgC submission on owner interruption; resumed same training image and accepted. Modal is not rejection until confirmed; corrected row48 after actual rejection observed.
