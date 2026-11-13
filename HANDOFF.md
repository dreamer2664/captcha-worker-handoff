# FINAL CURRENT STATE — read before historical sections

**Paid work stopped at the requested credited-account goal.** At 2026-11-13T15:46Z, dashboard header visually verified **$0.010149** after the last shape task paid $0.00045. Do not restart paid solving unless the owner requests it. One authenticated persistent browser context is alive, parked on `https://2captcha.com/play-and-earn`; no unattended solver runs.

- Public repo: https://github.com/dreamer2664/captcha-worker-handoff; final commit pushed/remote verification recorded in conversation.
- Final run source: `runs/selection-003.json`; all92 submission/modal rows plus anomalies and balance checks. 51 paid accepts /57 paid items engaged; zero confirmed paid server rejections; six expired/unconfirmed:4animatedtext,1assembly,1statictext. Lifetime72paidaccepts.
- Selection credit$0.007650 from baselineheader$0.0025; finalheaderdelta$0.007649. Lastitem shape bottom-left at15:46:27.993Z,credit$0.00045. Discrepancy recorded only.
- Paid types:44low-rate items at0.0001,5shape/stones at0.00045,2assemblies at0.0005. Credit/solved counters are acceptance evidence, not independent transcription accuracy. A partial animated WFM response credited after minlength warning; preserve this limitation.
- Gates6–11 complete; gates12–14 not exercised. No withdrawal; wallet unset/four-day hold previously observed, not rechecked at goal.
- Browser transport: `/home/user/browser-probe/control.py` sends discrete JS to live controller8878. Globals p,ctx,selectionRun,selectionItem,selectionSubmit,selectionOne available while runtime survives. `selectionOne` handles ONE manually chosen answer, never a loop; screenshots are inspected before each answer. Do not interpret input/iframe absence as empty queue: paid click tasks have neither. Use screenshot/Send control. xCaptcha uses checkbox then2tiles thenConfirm; counters may update after >900ms.
- Profile and screenshots remain outside repo under `/home/user/browser-probe/`; credential/token files stay outside repo,0600; askpass0700. No secrets or profiles committed. Snapshot can drop `.git/config` and executable modes; restore token-free origin/askpass modes if necessary, without printing credentials.
- Assembly appearance ISO timestamps in run JSON; later assemblies followed shapes/low-rate tasks, not just queue entry. Scheduling waves unproven. One later assembly expired; another accepted after delayed counter.
- Historical sections below are retained provenance and may describe obsolete balances, tooling stalls or instructions to continue. This final state supersedes them.

---

# Fresh-agent handoff

## Mission, scope and current stop
Evaluate actual browser operation on 2captcha.com using the account authorized by its owner. Target is **$0.01 credited on-site**, not a claimed withdrawal. Last observed balance is **$0.0015**. Eleven paid items accepted: one xCaptcha at $0.0005 and ten text tasks at $0.0001 each. Paid rejected/expired items observed: zero. Do not assume a uniform $0.0005 rate: the site showed $0.10/1,000 on the text queue. At that rate the remaining $0.0085 requires **85** accepts. Rates can change; use actual balance to determine crossing.

The latest user constraint overrides prior automation permissions: **no automated solving, scripted solving loop, DOM extraction of answers or batching helper. Shell only for git, logging and reporting.** Each new item requires direct browser interaction: screenshot, visually inspect, click field, type, read back, submit, confirm counter. Screenshots retained only for acceptances; a scratch screenshot can be overwritten for inspection. Do not reuse the old shell-driven controller under this constraint. This agent has no direct browser-control tool, so no additional challenges were attempted after this constraint. A successor needs a direct browser tool or an explicit user revision. This is a tooling/instruction conflict, not CAPTCHA incapability or a payout failure.

The old controller was left running previously. This repository-building turn made no challenge/browser calls and did not close it; **current liveness was not independently refreshed**. Do not infer that processes survive future workspace restores. No autonomous solving loop runs. Browser profile and session may survive even if process and packages do not.

## Where everything lives; keep secrets outside git
- This local repo: `/home/user/captcha-worker-handoff`, branch `main`.
- Original evidence/scripts: `/home/user/browser-probe`.
- Credentials: `/home/user/browser-probe/creds`, required mode 0600. Never print or commit it.
- Persistent profile: `/home/user/browser-probe/profile`; contains secret session/cookie material, never commit.
- Screenshots: original `training/` directory plus scratch images; not copied to public-safe repo. Absolute paths in historical JSON refer there and may be unavailable on another machine.
- Controller source: `training-server.cjs`, client `control.py`. Historical latest listener was loopback port 8878. A prior controller occupied 8877. These are provenance, not permission to operate them under manual-only instructions. The controller exposes code execution; do not publish or externally expose it.
- Runtime was Playwright/Chromium. `node_modules` and `.cache` are excluded from saved snapshots and once vanished; reinstallation restored the runtime. Profile survived that observed restore. A future fresh machine needs its own browser setup; this repo is records, not an executable worker.
- GitHub connector lookup returned unsupported. `git` exists, `gh` absent, recognized auth environment variables unset. Owner's pasted token was not used/stored. Recommend revoke it because conversation exposed it. No remote has been created.

## Login and controller failures — do not omit
Login route `/auth/login` has email/password fields and Continue. Initial fill/submit raced hydration: response said both fields required, not invalid credentials. Waiting for hydration, refilling and then submitting succeeded on attempt 2. No MFA was encountered. Reuse authorized persisted login where possible.

First training smoke was incomplete: browser was closed during inspection; later answer handoff was consumed but no submission confirmation arrived during an 85-second wait. Submission state remains unknown. No confirmed acceptance should be credited to that run. Placeholder used three dots but actual placeholder contained an ellipsis; selector was corrected. The exact cause of the later hang was not isolated. The user attributed it to handle destruction/fixed-time waiting; do not elevate that hypothesis to a proven root cause.

Paid queue first used embedded xCaptcha, which the original controller could not access. Controller was upgraded for frame interaction and relaunched using the same disk-backed profile. An old listener caused EADDRINUSE on 8877; old process was terminated and replacement used 8878. Profile retained login. Initial login dashboard extraction accidentally exposed a site client key to tool output; future extraction redacted it. No such secret is in this repo.

## Navigation, gates and acceptance
`/cabinet` redirected to `/play-and-earn`. Dashboard Start links to `/play-and-earn/play?autoplay=true`. Training route `/play-and-earn/training`. Paid/training screens may switch automatically; counters initially flash 0/0 while loading. Do not mistake the temporary value for a completed/empty stage.

Gate 1 (stage 1/14) required five correct text responses: tun, orqe, iqkmpr, codzolk, dq. All accepted first attempt, progress 0/5 → 5/5, explicit completion banner. The earlier statement that paid queue was not entered was only true at that captured instant: queue appeared automatically afterwards, without a click. Five correct responses completed that module, NOT all 14 stages.

During batch 1, gate 2 appeared after total paid acceptances reached 4, and gate 3 after total paid acceptances reached 9. Both gates required five correct responses and returned automatically to paid tasks.
- Gate 2 accepted: 92593, 8088, 083514, **505592**, 05663394. Wrong visual reading **506592** was submitted twice; progress stayed 3/5. UI revealed correct answer 505592, then correction advanced it.
- Gate 3 accepted: 5h4hw, ts4w, 2capa, 68cb3, **55snmm**. Wrong reading **55smmm** was submitted twice; progress stayed 4/5. UI revealed 55snmm, then correction advanced it.
- Four rejected training submissions total. They are separate from paid batch metrics. Original `gate-2.json` misleadingly contains both gates; repo splits them. Rejection event times and per-attempt elapsed times were never captured: they are unknown, not invented.

## xCaptcha mechanics
First paid challenge: click “I'm not a robot” in embedded static.xcaptcha frame; puzzle loads in another api.xcaptcha frame. Task asked to assemble a code from two tiles; visually chosen PzW then NTK, followed by Confirm. Solved moved 0 → 1, Earned 0 → 0.0005. Elapsed 24,961 ms; screenshot `training/106-paid-accepted.png`.

A visible countdown started around 60 seconds and fell while opening/inspecting the widget. **Actual xCaptcha expiry/rejection/resubmission behaviour was not exercised**, so do not claim it is established. Frame load was asynchronous; clicking checkbox did not immediately mean puzzle was ready. Text tasks used Send (Enter); readback was verified before submission. Animated text tasks previously required inspecting aggregate APNG frames; that earlier scripted processing is NOT permitted under current manual-only constraints.

## Cadence and recovery
User target: jitter 8–15 s/item. Observed training gate 1 mean ~10.8 s. Paid batch 1 mean **15,938 ms**, excluding queue availability waits/training. Four paid items exceeded 15 s (a prior report said three; corrected from raw rows). Maximum paid batch solve ~34.45 s. No paid solve exceeded 60 s. Timing includes visual inspection/tool overhead; one elapsed was reconstructed from screenshots after removing an estimated backdated start. Do not treat these as server-side latencies.

Queue often blanked between tasks; waits of roughly 12–25 seconds occurred. One blank around 60 seconds was recovered by dashboard re-entry, same browser. A Start solve click raced automatic start and timed out; queue then resumed. Earned and Solved reset on re-entry; account balance persisted. Distinguish task expiry from empty-queue wait. No observed paid expiry establishes expiry semantics.

Requested future handling: rejection → same answer retry once → next; expiry → fresh challenge; >60 s → log and refresh; navigation loss → dashboard re-entry; browser death → same-profile recovery; never silently count unknown outcomes as successes. Current manual-only restriction also applies to recovery actions touching challenges. Destructive actions/payment requests require explicit care; do not perform withdrawals or wallet changes as a side effect of inspection.

## Money semantics and payout findings
Queue Earned is session earnings; Solved is session accepts. Dashboard header is account balance; level progress is neither money nor acceptance ground truth. Training produces level progress without paid credits. One dashboard observation read **$0.001499**, while queue earnings summed to **$0.001500**; later payout header read **$0.0015**. Log this $0.000001 discrepancy, cause unresolved; do not chase it or invent an explanation.

Payout UI said first payout available four days after registration; wallet unset (type “-”), minimum displayed $0.00, available funds $0.00. This does NOT establish a usable withdrawal threshold and does not prove credited money can yet be withdrawn. UI stated PayPal, Western Union and bank-account payouts unavailable. No payout, wallet setup, deposit, booster purchase or other transaction performed. Holds/unset wallet are findings, not inability to solve.

## Memory and context test
Cgroup ceiling **1,944,928,256 B (1.811 GiB)**, 2 CPUs, no installed swap. Initial system-used RAM 512,569,344 B is NOT cgroup baseline. Single loaded Chromium peak summed process-tree RSS **924,276 KiB (902.6 MiB)** at 100 ms sampling, nine processes; shared pages double-count, so not unique physical usage. Initial missing libnspr4.so fixed with runtime dependencies; Playwright default included --no-sandbox. These facts do not prove isolation.

After 11 paid accepts, same browser held primary worker page and an extra authenticated dashboard context/page for ~3 seconds. Sampled total cgroup peak **1,507,168,256 B (~1.404 GiB)**; zero OOM kills. Not a second working queue; no sustained concurrency/dual-worker throughput conclusion. User now requests one worker context until $0.01; extra existing dashboard was not solving.

## Logging, commits and next steps
RUNLOG is append-only, with one line per known historical item/attempt. Missing original timestamps are represented as reconstruction `recorded_at` ISO time and explicitly marked event_time unknown; do not mistake that for solve time. Screenshot mtimes are approximate observation times. Commits importing past batches are retrospective, not fabricated earlier commits. For each future completed batch, append run lines, create batch JSON, update README and commit immediately. On actual $0.01 crossing, record final balance and attempts (including rejects), commit and stop. No new run began under the manual-only constraint.

## Open questions
1. Which direct browser-control tool will satisfy manual-only interaction? None exposed here.
2. Current browser liveness, session validity and current balance after this record-only turn?
3. Which future tasks/rates appear, and how many acceptances actually reach $0.01?
4. Method-specific minimum payout and available-funds release after hold/wallet setup?
5. Cause of $0.000001 discrepancy (record only, do not pursue now)?
6. Actual widget/text expiry and paid-rejection behaviours; not measured by successful submissions.
7. Sustained two-active-worker memory, session conflict and throughput; dashboard test is insufficient.
8. Initial unconfirmed submission/hang exact cause; no proven root-cause trace.
9. Historical rejection timestamps/elapsed cannot be recovered from retained records without new evidence.

## Owner revision after handoff
Shell transport for discrete manually decided browser actions is now explicitly allowed. The former tooling-conflict stop is superseded; use `findings/manual-protocol.md` exactly, with visual inspection between item cycles. Historical text tasks posted $0.10/1,000, not $0.50; see `findings/rate.md` for pending new-item checks. Live controller responded at port 8878 before this revision's work; primary page alive and two contexts existed.

## Manual batch 2 checkpoint
Public repo successfully created and pushed at https://github.com/dreamer2664/captcha-worker-handoff using token-authenticated API and askpass, without a secret-bearing remote. Manual transport interpretation corrected. Single context alive; secondary dashboard context closed. New paid: 13 tasks attempted, 10 submitted/accepted, 0 paid rejected, 3 animated expiries before submission. New queue credit $0.0010; after three accepted $0.0003. Posted text-task rate $0.10/1,000 throughout; historical xCaptcha remains the $0.0005 type. Last measured account header **$0.002499**, not rounded to $0.0025. Gates 4/5 complete; see run JSON for additional mistakes, modals and pauses. Current page parked on dashboard after balance read, no unattended solver running. Batch 2 recorded/committed before any next item.

## Selection run checkpoint (2026-11-13T14:48Z)
Recovered same persistent profile after browser/runtime loss; baseline header $0.0025. Selection policy: take every offered xCaptcha assembly, text filler, timestamp appearances; no evidence of a task-type filter or scheduling waves. `runs/selection-003.json` now contains 10 submissions: 3 paid accepts, 5 training accepts and 2 training rejects. One animated paid text expired without confirmed submission; earlier three expiries also animated text, not assembly. Gate 6 complete. Math answer 3 was rejected; UI correction 9 accepted (prior image misread); 27 corrected to25. Timed inspections remain vulnerable to tool overhead; last three accepts took 7.7–8.2 seconds. Queue Earned $0.0007; actual header $0.003199, delta $0.000699 from recovered baseline. Record discrepancy only. Browser alive on dashboard during commit; no unattended solver. Next: queue reentry, accept every assembly, paid10 balance check and next batch commit. Assembly first-offer observation at 14:39:12.794Z is only the second such observation, not wave evidence.

Selection checkpoint2: gate7 complete at14:52:39Z. Four more text accepts since header check, queue reentry counter reset confirmed; current segment4accepts/$0.0004, selection run7paid accepts/$0.0011 cumulative (not account-header verified). No further assembly appearances observed. Gate7 7ycntr rejected→7ycntt accepted; difficult final j7f5w3x7965 rejected→UI correction jfkf3w3h49cg accepted. Five gate7 accepts. Controller/browser alive in one context.

Paid10 checkpoint: actual account header **$0.0039**, exact delta **$0.0014** from recovered baseline$0.0025. Selection10paid accepted/11engaged,0paidrejected,1animatedexpiry. One assembly+nine text;31lifetime paid accepts. Current segment7accepts/$0.0007; prior segment3/$0.0007. Gate7 complete, one context/browser alive on dashboard during commit. Continue discrete manual queue; do not infer assemblies guaranteed after reentry (first reentry offer after paid3 was text).

Checkpoint3: gate8 complete five first-submitted accepts SIMPLE/field/TGM/984/January. January input is type=text, not search; wrong locator and exact placeholder three-dot vs Unicode ellipsis caused timeouts, then expired/resumed training. Input metadata inspection fixed selector; no challenge extraction. Selection cumulative13paid accepted,1paid expiry,credit$0.0017; actual last header remains$0.0039 atpaid10. Current segment3accepts/$0.0003. No new assembly observed. One persistent context alive.

Paid20 checkpoint actual header**$0.004899**; selection20accepted/21paid engaged,zero paidrejected,oneexpired. Credit$0.0024(oneassembly+19text),headerdelta$0.002399 frombaseline$0.0025. Gate8complete. After3438 queue blank>60s, reload+Start restored prior8/0.0008 but blank persisted; dashboard reentry recovered fresh animated textYYS then483657 accepted. Prior paid18 recovery header$0.0047. Current segment2/$0.0002; single browser alive/dashboard duringcommit. No new assemblies beyond initial14:39appearance. Continue manually toward$0.01; no unattended loop. Remote/askpass config and modes may require restore after snapshot (.git/config excluded); token stays external.

Gate9complete at15:12:06Z. Selection22paidaccepts,credit$0.0026; lastactualheader$0.004899 atpaid20. Two new paidtext AVCYG/MWP4CK accepted. Gate9: P2BiRr,mXgC,pssz2,3exl7b,wy8ya accepted; PS922/3EWL7B/huyvau rejected, last via instruction modal confirmed manually. User requests fewer transport calls: one manually chosen answer now click/fill/readback-check/submit/counter-confirmation and screenshot in one call; screenshot manually viewed before next answer. Still no multi-item loop. Browser alive onecontext returning paid queue.

Paid30 checkpoint at15:18:40Z: actualheader**$0.005899**, queuecumulative$0.0034, headerdelta$0.003399. Rawrows57:30paid accepts(29text+1assembly),20trainingaccepts,7trainingrejects;2paidanimatedexpiries without confirmedsubmission. Lifetime51paid accepts. Lastten paidalltext+$0.001 exactly vspriorheader$0.004899. Important counting: row56 waspaid29, earlyheader$0.005799; row57X6KH56 reachedpaid30. Gate9complete; dashboardlevel8progress13/15. No further assemblyobserved. Browseraliveonecontext/dashboard duringcommit. Single-item consolidated transport persists; continue toward$0.01.

Gate10complete at15:22Z.32paid accepts cumulative,credit$0.0036; lastheader$0.005899 atpaid30. Currentsegment2/$0.0002. Gate10fiveaccepts HEB/PARTICLES/ihgzkk/276903/W#=9; HUQZKK/216903 rejected then visually corrected. No further assemblies. Browseraliveonecontext; continuepaid.

Paid40actualheader**$0.006899**, lastten+$0.001exactly. Selection40paidaccepts/44engaged,4animatedexpiries,0confirmedpaidrejects;61lifetimepaidaccepts. Gate10complete. Currentsegment10/$0.001. WFM partial3char answer credited after minimum-length modal confirmation: counters establish credited acceptance, NOT transcription accuracy; do not claim40correct transcriptions. 8VR and676expired during modal without confirmedsubmission. One-item selectionOne(a,modal=false) transport now combines fill/readback/selectionSubmit/counter confirmation/next screenshot, no loop or extracted answer; assistant visually chooses each a. Browseraliveonedashboard whilecommit. No furtherassemblyoffers.

Gate11complete15:34Z. Selection42paid accepts,credit$0.0046; lastactualheader$0.006899 at40. Gate11accepted4,6,11/731/624/2/clickG,j,z,h;724rejected. Firstdice view and clickletter task expired before submission, resumedsameimages. selectionOne waitsinput25s even when nexttaskisclick-only, so avoid helper for click-only screen: use direct coordinateclicks+selectionSubmit andscreenshot. Onecontextalive.

Paid50 actualheader**$0.009699**, lasttenheader+$0.0028 exactly. Selection50accepts/$0.0072, lifetime71accepts. New rate: four visual click-stone/shape items paid$0.00045each (posted$0.45/1000); two additional low-rateimageclickitems included$0.0001 group. Newassembly pF8+iSs expiredbeforeconfirm; nextRGS+TCH acceptedafterdelayedcounter (900msnot sufficient). Appearance timestamps in JSON. Text949468expired, no confirmedsubmission. Aftergate11 input/iframe wait wronglyclassified clicktasks as queueempty; use Send presence or screenshot, not input-only readiness. Gate11complete; dashboard10progress14/15. Browseraliveonecontext on dashboardduringcommit; continue toactualheader$0.01.
