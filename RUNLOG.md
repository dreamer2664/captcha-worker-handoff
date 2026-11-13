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
