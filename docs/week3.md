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
before running the commands my expected outcome for when i do in fact do this is | Application       | Expected CPU Usage | Expected RAM Usage | Expected Disk Usage | Expected Network Usage | Notes                                          |
| ----------------- | ------------------ | ------------------ | ------------------- | ---------------------- | ---------------------------------------------- |
| `stress-ng` (CPU) | Very High          | Low                | None                | None                   | CPU cores will run at 100% load.               |
| `stress-ng` (RAM) | Medium             | Very High          | None                | None                   | High memory allocation may cause swapping.     |
| `fio`             | Low-Medium         | Medium             | Very High           | None                   | Disk read/write throughput will dominate.      |
| `iperf3`          | Low                | Low                | None                | Very High              | Network bandwidth will be saturated.           |
| `nginx`           | Low–Medium         | Low                | Low                 | Medium                 | Load increases when HTTP traffic is generated. |



