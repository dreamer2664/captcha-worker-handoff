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
