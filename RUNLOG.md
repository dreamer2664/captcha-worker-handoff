# Append-only item log

Columns: ISO timestamp | index | answer | outcome | elapsed_ms | provenance.
Historical entries are reconstructed from saved artifacts, not contemporaneous logging. `recorded_at` timestamps mark reconstruction when event timestamps are unavailable. `unknown` means unmeasured, never zero. Screenshot mtimes are approximate observation timestamps, not verified server acceptance timestamps. Rejected training attempts had no saved per-attempt timestamp or elapsed measurement. Append corrections; do not edit old entries.

