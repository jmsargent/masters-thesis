
# Dictionary

Course grained - one single frequency setting for the entire duration of the application

Fine grained - DVFS per kernel call

Phase based DVFS - Multiple consecutive kernels defined as a phase ran at optimal frequency

Pareto front - the set of optimal solutions where one solution can not be improved without compromizing another solution

One shot profiling - Run app once to get baseline data to use for energy prediction model


## Summary

* Memory bound kernels do not benefit much from DVFS, however compute-bound kernels do

* The overhead from frequency tuning can be hidden behind the latency of communication between graphic cards (CPU-GPU communication) 

* Clustering algoritm was most promising for finding phases

## Thoughts

* There might be differences in latencies for GPU-GPU communication, compared to CPU-GPU communication, this could impact the ability to hide latency create a more fine/course-grained phase partition of the DAG. (Im guessing the latency is going to be lower, therefore that would decrease the ability to hide the latency of DVFS). 

* Question: what are the performance characteristics for inter/intra-node communication between GPUS? What technologies are used in MUSTARD

* Could we instead of or in addition to, change the cluster configuration to one more appropriate to the phase?
- probably orders of magnitude slower to do
+ could affect both compute and memory bound kernels
+ since cloud, the problem of access

* The synergi API for dvfs seems interesting for DVFS
