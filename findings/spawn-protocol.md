# Fresh-instance spawn protocol

## Read before doing work
Read HANDOFF.md, findings/manual-protocol.md, findings/worker-access.md, findings/rate.md and runs/handoff-status.json. Historical stop-at-$0.01 is superseded by target $0.02. Exact baseline $0.010149; no subsequent paid items. Only >=3x text rates; accuracy over speed. No registration or second account.

## Persistent profile and controller
Local private runtime: /home/user/browser-probe. Profile: profile/. Controller: training-server.cjs. Python transport: control.py, stdin JavaScript forwarded to loopback 8878; globals p, ctx, chromium, fs, shot. These runtime/profile/credential files are NOT public repo assets. First probe existing listener/browser before starting anything. Keep browser alive and parked during git operations and turn end. One context; memory ceiling 1,944,928,256 bytes.

If restoring has removed dependencies, from the runtime directory run `npm ci` then `npx playwright install chromium`. Package manifest records playwright ^1.65.0; lockfile determines version. Cache/node_modules are excluded from snapshots. Missing browser executable and missing module are restore failures, not login failure. Do not overwrite existing controller/profile. If controller is gone and profile lock is not held by a live browser, use the background-process tool to run `node training-server.cjs` in that directory. It starts the persistent profile and listener 8878. Never launch a second owner of that profile. If controller is alive but browser closed, use its transport to relaunch the same persistent profile, reuse first page, then inspect authentication. Three technical attempts maximum; log/escalate after that.

## Login and navigation
Prefer preserved cookies. If login appears, allow hydration, fill existing authorized credentials from private local storage without printing them, inspect state, then submit. Initial historical hydration race produced missing-fields validation; refill after hydration succeeded on attempt two. Stop for MFA or actually rejected credentials. Credential files 0600; never copy into repo/output. Dashboard can expose a client/API key, so no raw body dumps or public dashboard screenshots. Redact before writing logs.

Existing same-account /job and /enterpage work. /cabinet redirects to Play & Earn even in classic mode. Worker detailed FAQ is /support/faq/worker; wait for hydration before reading questions. Do not infer a legacy queue exists.

## Discrete per-item cycle
Use the exact shell transport sequence in manual-protocol.md. Capture screenshot, open with file viewer, visually read twice. Select controls only; no challenge-answer extraction from DOM, images metadata, network, alt text or OCR. Click/type the ONE visually chosen answer, read input back, submit once, observe accepted/progress counter and save screenshot. One consolidated transport is allowed for a pre-inspected single item; no unattended multi-item loop. For widgets use visually selected tiles and frame Confirm. Never reuse an answer after task change without looking again.

Counter updates can lag >900 ms after xCaptcha Confirm; condition-wait before deciding failure. Modals are not rejections. Training: capture filled/progress state; unchanged retry once then fresh task; no balance checks mid-training. Complete later gates if encountered. Session solved counters reset on dashboard reentry; cumulative ledger is authoritative.

## Timer and quality discipline
Target 8–15 seconds with jitter only when compatible with correctness. Accuracy is currency; read twice, do not rush to manufacture throughput. Imperfect submission only if a hard timer forces that tradeoff. >60 seconds: log and refresh. Expired task: fresh challenge, never stale submit. Rejected: retry once only after visual reinspection. Prefer safe skip/control if available; do not assume a type filter. Log assembly appearance timestamps, not supposed waves. No low-rate filler under current rule.

## Accounting and publication
Read exact balance after new paid items 3 and 10; log attempted, accepted, unknown/expired, offered rate, measured deltas. Log displayed rating every ten, or explicitly unavailable; never infer it from level. Stop type below any published threshold. Commit each ten. One-millionth discrepancy is record-only. Four-day hold and unset wallet are not work blockers; do not withdraw.

Repo: https://github.com/dreamer2664/captcha-worker-handoff, main. Check git diff and staged files for secrets. Never add profile, creds, client keys, tokens or raw dashboard images. Existing private askpass can push: `GIT_ASKPASS=/home/user/.repo-askpass GIT_TERMINAL_PROMPT=0 git push origin main`. Remote URL must stay token-free. Confirm with ls-remote; retain browser. Secret files/askpass are local pre-existing prerequisites, not included in handoff. Public repo alone does not contain login credentials or private profile.
