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

2026-11-13T14:39:38.476Z | S3-1 | K9C + G6Z | accepted xcaptcha-assembly | 33902 | discrete visual/manual; selection-003.json
2026-11-13T14:42:11.686Z | S3-2 | 1q291e | accepted text | 25726 | discrete visual/manual; selection-003.json
2026-11-13T14:43:42.749Z | S3-3 | 32 | accepted training | 25847 | discrete visual/manual; selection-003.json
2026-11-13T14:44:15.746Z | S3-4 | 27 | rejected training | 26077 | discrete visual/manual; selection-003.json
2026-11-13T14:45:30.729Z | S3-5 | 25 | accepted training | 23296 | discrete visual/manual; selection-003.json
2026-11-13T14:46:06.896Z | S3-6 | 3 | rejected training | 27455 | discrete visual/manual; selection-003.json
2026-11-13T14:47:23.557Z | S3-7 | 9 | accepted training | 21905 | discrete visual/manual; selection-003.json
2026-11-13T14:47:34.673Z | S3-8 | 8-4+2 | accepted training | 7728 | discrete visual/manual; selection-003.json
2026-11-13T14:47:45.556Z | S3-9 | 6 | accepted training | 8209 | discrete visual/manual; selection-003.json
2026-11-13T14:48:25.697Z | S3-10 | RK8VY | accepted text | 7953 | discrete visual/manual; selection-003.json
2026-11-13T14:41:00.759Z | S3-expiry-1 | unknown | expired animated text, no confirmed submission | unknown | five-second target missed
2026-11-13T14:39:12.794Z | S3-assembly-appearance-1 | n/a | offered $0.50/1000 | n/a | first offer after recovered-profile reentry; not proof of waves

2026-11-13T14:49:33.854Z | S3-11 | R9A38 | accepted text | 9130 | discrete visual/manual; selection-003.json
2026-11-13T14:50:01.240Z | S3-12 | 9W8K7 | accepted text | 9780 | discrete visual/manual; selection-003.json
2026-11-13T14:50:25.616Z | S3-13 | 4HGB | accepted text | 10814 | discrete visual/manual; selection-003.json
2026-11-13T14:50:41.586Z | S3-14 | 5U7V2 | accepted text | 10662 | discrete visual/manual; selection-003.json
2026-11-13T14:51:02.163Z | S3-15 | 7ycntr | rejected training | 13477 | discrete visual/manual; selection-003.json
2026-11-13T14:51:17.604Z | S3-16 | 7ycntt | accepted training | 12150 | discrete visual/manual; selection-003.json
2026-11-13T14:51:35.480Z | S3-17 | JQA3Lg | accepted training | 13836 | discrete visual/manual; selection-003.json
2026-11-13T14:51:51.079Z | S3-18 | PXAZGC | accepted training | 11577 | discrete visual/manual; selection-003.json
2026-11-13T14:52:07.745Z | S3-19 | SMV6BR | accepted training | 11977 | discrete visual/manual; selection-003.json
2026-11-13T14:52:24.482Z | S3-20 | j7f5w3x7965 | rejected training | 13700 | discrete visual/manual; selection-003.json
2026-11-13T14:52:39.888Z | S3-21 | jfkf3w3h49cg | accepted training | 11179 | discrete visual/manual; selection-003.json

2026-11-13T14:53:15.617Z | S3-22 | 87rnf | accepted text | 14266 | discrete visual/manual; selection-003.json
2026-11-13T14:53:45.441Z | S3-23 | 3CBG | accepted text | 12212 | discrete visual/manual; selection-003.json
2026-11-13T14:54:07.724Z | S3-24 | 878401 | accepted text | 13231 | discrete visual/manual; selection-003.json

2026-11-13T14:56:03.153Z | S3-25 | 267955 | accepted text | 13712 | discrete visual/manual; selection-003.json
2026-11-13T14:56:31.896Z | S3-26 | 4FWYBS | accepted text | 10718 | discrete visual/manual; selection-003.json
2026-11-13T14:56:51.817Z | S3-27 | SIMPLE | accepted training | 12958 | discrete visual/manual; selection-003.json
2026-11-13T14:57:09.216Z | S3-28 | field | accepted training | 13337 | discrete visual/manual; selection-003.json
2026-11-13T14:57:28.883Z | S3-29 | TGM | accepted training | 13477 | discrete visual/manual; selection-003.json
2026-11-13T14:57:48.449Z | S3-30 | 984 | accepted training | 11648 | discrete visual/manual; selection-003.json
2026-11-13T14:58:59.657Z | S3-31 | January | accepted training | 13544 | discrete visual/manual; selection-003.json
2026-11-13T14:59:20.445Z | S3-32 | HU0P5K | accepted text | 12546 | discrete visual/manual; selection-003.json

2026-11-13T14:59:51.594Z | S3-33 | TPMD | accepted text | 18276 | discrete visual/manual; selection-003.json
2026-11-13T15:00:25.109Z | S3-34 | P4AV | accepted text | 15526 | discrete visual/manual; selection-003.json
2026-11-13T15:01:00.728Z | S3-35 | 89Q16 | accepted text | 30149 | discrete visual/manual; selection-003.json
2026-11-13T15:01:34.895Z | S3-36 | M5KND | accepted text | 16263 | discrete visual/manual; selection-003.json
2026-11-13T15:02:08.307Z | S3-37 | 3438 | accepted text | 15697 | discrete visual/manual; selection-003.json

2026-11-13T15:05:36.970Z | S3-38 | YYS | accepted text | 28870 | discrete visual/manual; selection-003.json
2026-11-13T15:06:06.730Z | S3-39 | 483657 | accepted text | 16163 | discrete visual/manual; selection-003.json
2026-11-13T15:03:20Z | S3-recovery | n/a | blank queue >60s, reload then dashboard reentry | unknown | successful recovery; no paid loss observed
