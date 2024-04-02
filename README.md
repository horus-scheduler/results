# Results
This repository contains the Horus data and raw output logs.

Experiment data can be downloaded from [here](https://drive.google.com/drive/folders/1R8Ft5yP_Z3LLx5A36_p79JrjHpkOYCsS?usp=sharing). It includes the data collected from our testbed and simulation experiments.

## 1.  Simulation Experiments
- Output files for the main large-scale experiments with different workloads are added.
- We include the analysis output from the simulator for all workloads, which outputs the different percentiles for all worker pools in one file. 
- For reference, we added the complete raw output data (in addition to analysis summary files) for the bimodal workload. 

In addition, we have included experiments for single-rack setups and the impact of per-hop latency and packet loss on Horus under this folder. 

> Please note that in our simulator output files the policy names are as follows:
>1. "adaptive" refers to Horus's policy. 
>2. "random_racksched" refers to RackSched with uniform load balancing (RS-LB).
>3. "racksched" refers to hierarchical RackSched (RS-H). 

## 2. Testbed experiments
Data for each scenario's is under a separate folder. 
- For TPC workloads and RocksDB 90%GET-10%SCAN, we provide an analysis file in CSV format that shows the 99th percentile, 50th percentile, and mean response time for each load.
- For all other experiments, the raw collected response times for all tasks are included, and each file contains data for a single point in our plots, which represents a fixed workload under a fixed hardware setup at a certain load.

- Additionally, each folder contains a file named overhead.txt, which includes the raw logs collected from the Tofino switch, showing overheads in terms of resubmitted packets and the number of update messages sent. 

- We  provide scheduling latency results for a single experiment under "result_scheduling_latency".


 
>File naming convention notes: 
>1. "db_bimodal": refers to RocksDB workload with 90%GET 10%SCAN distribution.
>2. "db_port_bimodal": refers to the RocksDB workload with 50%GET-50%SAN distribution.
>3. "Saqr": Some of the old collected data still might refer to "Horus" as "Saqr" policy. 

---

> **Please note that the collected numbers in testbed experiments are in *nanoseconds*, while the numbers in simulations are in *microseconds*.**
