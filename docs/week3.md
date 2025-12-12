# Week 3 — Application Selection for Performance Testing

During Week 3, I prepared my system for performance evaluation by selecting applications that represent different workload types, installing them via SSH, and planning how I will monitor each workload in Week 6.
The goal of this week is not to run tests but to prepare a structured and justified testing methodology.


To evaluate how the operating system behaves under different workloads, I selected one application for each of the required workload categories.
These tools were chosen because they provide predictable, repeatable, and measurable performance pattern.
**This is my matrix table**
| Workload Type | Application | Reason |
|---------------|-------------|--------|
| CPU | stress-ng | Creates repeatable CPU load |
| RAM | stress-ng (vm mode) | Allows controlled memory allocation |
| Disk I/O | fio | Industry standard disk benchmark |
| Network | iperf3 | Measures upload/download throughput |
| Server | nginx | Lightweight web server for load testing |

By selecting these tools, I ensured that each major subsystem (CPU, RAM, disk, network, server processes) can be tested in a way that produces meaningful data

After i went into my server in Ubuntu and indicidually wrote these commands to install these tools the commands were:
sudo apt update
sudo apt install fio -y
sudo apt install iperf3 -y
sudo apt install nginx -y
before running the commands my expected outcome for when i do in fact do this is

## 3. Expected Resource Profiles

| Application        | Expected CPU Usage | Expected RAM Usage | Expected Disk Usage | Expected Network Usage | Notes |
|--------------------|--------------------|--------------------|----------------------|-------------------------|-------|
| stress-ng (CPU)    | Very High          | Low                | None                 | None                    | CPU cores will reach 100% load. |
| stress-ng (RAM)    | Medium             | Very High          | None                 | None                    | High memory allocation may trigger swapping. |
| fio                | Low–Medium         | Medium             | Very High            | None                    | Heavy read/write workloads dominate performance. |
| iperf3             | Low                | Low                | None                 | Very High               | Network bandwidth will be saturated during tests. |
| nginx              | Low–Medium         | Low                | Low                  | Medium                  | Resource usage increases under HTTP request load. |

Monitoring Strategy

This section outlines how I will measure performance for each application.
The strategy ensures consistent and repeatable data collection.

the tools ill use for monitoring are 
top- live CPU,RAM and it loads up averages
vmstat1- Cpu wait time
free -h- memory pressure and swap usage
df -h - disk space usage
iperf3 - network throughput
ping- latency and packet loss
the tools mentioned here provide a complete view of system performance across CPU,RAM,disk and network subsystems

