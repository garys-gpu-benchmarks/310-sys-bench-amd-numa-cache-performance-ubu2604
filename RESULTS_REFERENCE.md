# Results: 310 NUMA Cache Latency Sweep

**Main goal:** Measure NUMA latency and penalties  
**Tools:** Build and run numa_sweep via collect_numa_cache.py, with numactl and optional perf stat

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_140 · recorded 2026-11-13). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 26.04.1 LTS · kernel 7.0.0-38-generic · driver 7.1.9.31600000
- **Run:** 2026-11-13T20:28:35Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 00:05 · benchmark 00:01 · whole run 00:14
- **Source:** run 310_20261113_202835
- **Command:** `bash run_benchmark.sh --smoke --source-numa-node 0 --target-numa-node 0,remote --num-threads 1 --thread-affinity strict --working-set-size 32768,2097152,268435456 --cache-level L1,L3,DRAM --access-pattern random --stride 64 --num-iterations 20000`

| # | Metric | Result |
|---|---|---|
| 1 | Largest cache-tier pointer-chase latency, ns (cache_latency_nsec) | 67.9001 |
| 2 | Local DRAM pointer-chase latency, ns (local_numa_node_latency_nsec) | 158.6766 |
| 3 | Pointer-chase payload rate, GB/s (local_dram_pointer_chase_bandwidth_gb_s) | 0.0504 |
| 4 | DRAM-tier cache misses/s (cache_miss_counters_misses_sec) | 44793865.838633 |
<!-- /profile:smoke -->
