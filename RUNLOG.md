# Append-only item log

Columns: ISO timestamp | index | answer | outcome | elapsed_ms | provenance.
Historical entries are reconstructed from saved artifacts, not contemporaneous logging. `recorded_at` timestamps mark reconstruction when event timestamps are unavailable. `unknown` means unmeasured, never zero. Screenshot mtimes are approximate observation timestamps, not verified server acceptance timestamps. Rejected training attempts had no saved per-attempt timestamp or elapsed measurement. Append corrections; do not edit old entries.

2026-11-13T12:25:48.335884+00:00 | T1-1 | tun | accepted | 9236 | screenshot_mtime; historical import
2026-11-13T12:25:56.023884+00:00 | T1-2 | orqe | accepted | 7687 | screenshot_mtime; historical import
2026-11-13T12:26:09.695884+00:00 | T1-3 | iqkmpr | accepted | 13669 | screenshot_mtime; historical import
2026-11-13T12:26:19.055884+00:00 | T1-4 | codzolk | accepted | 9363 | screenshot_mtime; historical import
2026-11-13T12:26:33.067884+00:00 | T1-5 | dq | accepted | 14010 | screenshot_mtime; historical import
