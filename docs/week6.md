for week 6 I am testing for: 
CPU,memory using stress-ng 
Disk I/O using sysbench
Network using iperf3
Server response using nginx

**Baseline performance**

<img width="365" height="50" alt="image" src="https://github.com/user-attachments/assets/881fc34a-c3de-4890-b92b-31de8d012cc7" />

we are focusing on cpu %


<img width="376" height="44" alt="image" src="https://github.com/user-attachments/assets/3ce57500-1403-4c3c-991b-090d03d86d70" />


now i will stress the system

<img width="453" height="89" alt="image" src="https://github.com/user-attachments/assets/7da8f61d-cbf7-47c0-9ac3-2f0a18f618d2" />

<img width="461" height="103" alt="image" src="https://github.com/user-attachments/assets/3743ee08-857d-409c-987d-6a445d310480" />

Latency tests

<img width="365" height="139" alt="image" src="https://github.com/user-attachments/assets/60a24c05-1f9d-451b-996b-caf08502397a" />

## Performance Measurement Table (Week 6)

| Application | Metric | Baseline | Under Load | Notes |
|------------|-------|----------|-----------|------|
| CPU (stress-ng) | CPU Usage (%) | 5% | 95% | High CPU saturation |
| Memory (stress-ng) | Memory Used | 1.2GB | 3.8GB | Increased memory pressure |
| Disk (sysbench) | I/O Ops/sec | 120 | 480 | Heavy disk activity |
| Network (iperf3) | Throughput (Mbps) | 0 | 940 | Near line speed |
| Network (ping) | Latency (ms) | 18 | 65 | Increased under load |


**Improvements**

Reduce SSH overhead by going into nano of ssh_config and ensuring UseDNS no after that the nano of the ssh will change and service will restart

second option is to enable performance tuning, by doing this and then re-testing the cpu test or network test it will show improved numbers

## Optimisation Analysis

Two performance optimisations were implemented and tested.

1. SSH configuration was optimised by disabling DNS lookups, reducing connection latency.
2. The tuned throughput-performance profile was enabled to optimise CPU and I/O scheduling.

Post-optimisation testing showed:
- Reduced system latency
- Improved CPU scheduling efficiency

Quantitative measurements confirmed performance improvements compared to baseline testing.
