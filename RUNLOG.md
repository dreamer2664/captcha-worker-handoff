# Append-only item log

Columns: ISO timestamp | index | answer | outcome | elapsed_ms | provenance.
Historical entries are reconstructed from saved artifacts, not contemporaneous logging. `recorded_at` timestamps mark reconstruction when event timestamps are unavailable. `unknown` means unmeasured, never zero. Screenshot mtimes are approximate observation timestamps, not verified server acceptance timestamps. Rejected training attempts had no saved per-attempt timestamp or elapsed measurement. Append corrections; do not edit old entries.

2026-11-13T12:25:48.335884+00:00 | T1-1 | tun | accepted | 9236 | screenshot_mtime; historical import
2026-11-13T12:25:56.023884+00:00 | T1-2 | orqe | accepted | 7687 | screenshot_mtime; historical import
2026-11-13T12:26:09.695884+00:00 | T1-3 | iqkmpr | accepted | 13669 | screenshot_mtime; historical import
2026-11-13T12:26:19.055884+00:00 | T1-4 | codzolk | accepted | 9363 | screenshot_mtime; historical import
2026-11-13T12:26:33.067884+00:00 | T1-5 | dq | accepted | 14010 | screenshot_mtime; historical import
2026-11-13T12:37:37.640440+00:00 | P1 | PzW + NTK | accepted | 24961 | screenshot_mtime; historical import
2026-11-13T12:38:18.036440+00:00 | B1-1 | 436K5T | accepted | 12782 | screenshot_mtime; historical import
2026-11-13T12:38:58.368440+00:00 | B1-2 | 5664 | accepted | 16532 | screenshot_mtime; historical import
2026-11-13T12:39:16.716440+00:00 | B1-3 | 976273 | accepted | 10313 | screenshot_mtime; historical import
2026-11-13T12:39:39.184440+00:00 | T2-1 | 92593 | accepted | 11846 | screenshot_mtime; historical import
2026-11-13T12:39:50.172441+00:00 | T2-2 | 8088 | accepted | 7284 | screenshot_mtime; historical import
2026-11-13T12:40:02.204440+00:00 | T2-3 | 083514 | accepted | 8496 | screenshot_mtime; historical import
2026-11-13T12:40:37.180440+00:00 | T2-4 | 505592 | accepted | 31624 | screenshot_mtime; historical import
2026-11-13T12:40:48.420440+00:00 | T2-5 | 05663394 | accepted | 7842 | screenshot_mtime; historical import
2026-11-13T12:41:21.828440+00:00 | B1-4 | 398794 | accepted | 12764 | screenshot_mtime; historical import
2026-11-13T12:41:49.276440+00:00 | B1-5 | PCX | accepted | 9880 | screenshot_mtime; historical import
2026-11-13T12:42:42.612440+00:00 | B1-6 | RLNUBZ | accepted | 34448 | screenshot_mtime; historical import
2026-11-13T12:43:13.560440+00:00 | B1-7 | MNTCG3 | accepted | 9274 | screenshot_mtime; historical import
2026-11-13T12:43:54.156440+00:00 | B1-8 | 3BF5Z | accepted | 18522 | screenshot_mtime; historical import
2026-11-13T12:44:24.772440+00:00 | T3-1 | 5h4hw | accepted | 20600 | screenshot_mtime; historical import
2026-11-13T12:44:36.540440+00:00 | T3-2 | ts4w | accepted | 7918 | screenshot_mtime; historical import
2026-11-13T12:44:52.704440+00:00 | T3-3 | 2capa | accepted | 10268 | screenshot_mtime; historical import
2026-11-13T12:45:04.360440+00:00 | T3-4 | 68cb3 | accepted | 7653 | screenshot_mtime; historical import
2026-11-13T12:45:46.060440+00:00 | T3-5 | 55snmm | accepted | 36287 | screenshot_mtime; historical import
2026-11-13T12:46:34.100441+00:00 | B1-9 | N2PA9 | accepted | 22898 | screenshot_mtime; historical import
2026-11-13T12:48:26.412440+00:00 | B1-10 | B5OHXP | accepted | 11975 | screenshot_mtime; historical import
2026-11-13T12:58:54.196330+00:00 | T2-retry-1 | 506592 | rejected; progress unchanged | unknown | recorded_at; event_time unknown; reconstructed from tool transcript
2026-11-13T12:58:54.196330+00:00 | T2-retry-2 | 506592 | rejected; progress unchanged | unknown | recorded_at; event_time unknown; reconstructed from tool transcript
2026-11-13T12:58:54.196330+00:00 | T3-retry-1 | 55smmm | rejected; progress unchanged | unknown | recorded_at; event_time unknown; reconstructed from tool transcript
2026-11-13T12:58:54.196330+00:00 | T3-retry-2 | 55smmm | rejected; progress unchanged | unknown | recorded_at; event_time unknown; reconstructed from tool transcript
2026-11-13T13:00:18.878665+00:00 | INITIAL-SMOKE | tun (read only; submission unknown) | unconfirmed | unknown | recorded_at; event_time unknown; retrospective correction: not counted accepted
2026-11-13T13:00:18.878665+00:00 | HANDOFF-TURN | none | no challenge actions; manual-only tooling conflict | unknown | record-only turn; no new attempts
2026-11-13T13:05:15.992Z | MANUAL-1 | R6N38M | accepted | 22524 | paid
2026-11-13T13:05:52.292Z | MANUAL-2 | F87M9Y | accepted | 18680 | paid
2026-11-13T13:06:28.358Z | MANUAL-3 | JDQMDM | accepted | 18466 | paid
2026-11-13T13:07:11.440Z | MANUAL-4 | Gdj5Lz | rejected-progress-unchanged | 22445 | training
2026-11-13T13:08:20.151Z | MANUAL-5 | gay5lz | accepted | 17593 | training
2026-11-13T13:08:42.169Z | MANUAL-6 | Ha7apb | accepted | 16644 | training
2026-11-13T13:09:06.283Z | MANUAL-7 | 5tpy7p | accepted | 18426 | training
2026-11-13T13:09:36.841Z | MANUAL-8 | P2Iw2 | unconfirmed-modal/progress-unchanged | 24517 | training
2026-11-13T13:10:20.143Z | MANUAL-9 | P2tw2 | unconfirmed-modal/progress-unchanged | 23201 | training
2026-11-13T13:12:09.076Z | MANUAL-10 | P21w2 | accepted | 6871 | training
2026-11-13T13:12:30.194Z | MANUAL-11 | [Cannot solve — instructed by training] | accepted | 13814 | training
2026-11-13T13:13:08.024Z | MANUAL-12 | 464422 | accepted | 17050 | paid
2026-11-13T13:14:55.173Z | MANUAL-13 | W3VPZG | accepted | 21449 | paid
2026-11-13T13:15:36.925Z | MANUAL-14 | BG34 | accepted | 24352 | paid
2026-11-13T13:16:14.333Z | MANUAL-15 | 6384ZQ | accepted | 19790 | paid
2026-11-13T13:16:50.748Z | MANUAL-16 | 5RHVH | accepted | 18689 | paid
2026-11-13T13:17:34.280Z | MANUAL-17 | nmkhv | rejected-progress-unchanged | 24144 | training
2026-11-13T13:18:44.293Z | MANUAL-18 | nmkhy | accepted | 23127 | training
2026-11-13T13:19:17.144Z | MANUAL-19 | 5e678 | accepted | 24791 | training
2026-11-13T13:19:44.224Z | MANUAL-20 | nat4iuu | accepted | 21241 | training
2026-11-13T13:20:07.837Z | MANUAL-21 | [Cannot solve — Cyrillic task] | accepted | 17825 | training
2026-11-13T13:20:30.976Z | MANUAL-22 | [Cannot solve — Cyrillic words] | accepted | 15379 | training
2026-11-13T13:23:47.631Z | MANUAL-23 | HCU6EN | accepted | 28992 | paid
2026-11-13T13:24:33.263Z | MANUAL-24 | V6MYWZ | accepted | 27852 | paid
2026-11-13T13:08:02.249Z | MANUAL-EVENT | none | expired/stopped before corrected answer could submit; no success counted | unknown | additional observed event
2026-11-13T13:12:02.152Z | MANUAL-EVENT | P2lw2 | rejected | unknown | additional observed event
2026-11-13T13:14:10.032Z | MANUAL-EVENT | none | paid animated task expired before fill; read F347 not submitted | unknown | additional observed event
2026-11-13T13:21:45.992Z | MANUAL-EVENT | none | paid animated task expired before HFBTG could be filled; no submission | unknown | additional observed event
2026-11-13T13:23:00.720Z | MANUAL-EVENT | none | paid animated task expired after ZVMA readback, before submit button action; no acceptance | unknown | additional observed event
2026-11-13T13:25:16.586750+00:00 | BATCH-2-CORRECTION | P2lw2 | rejected, visually observed correction P21w2 | unknown | was outside primary rows; event_time unknown
