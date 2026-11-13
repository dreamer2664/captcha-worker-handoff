# Memory
Cgroup limit 1,944,928,256 B (~1.811 GiB); nproc 2; no swap installed. Initial system-used RAM 512,569,344 B, not an initial cgroup reading. Single loaded-page browser process-tree sampled RSS 924,276 KiB (902.6 MiB), 100 ms sample, nine processes. Shared pages double-count in summed RSS.

Same browser two-context test: authenticated dashboard plus primary queue, 3 seconds, sampled cgroup peak 1,507,168,256 B (~1.404 GiB), zero OOM kills. NOT sustained dual-worker test. Initial browser needed libnspr4.so/runtime dependencies. Default --no-sandbox observed. Resource limits do not establish containment.
