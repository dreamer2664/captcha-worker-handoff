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
