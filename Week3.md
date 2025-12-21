# Application selection for performance testing
## Objective
The objective of this phase is to select representative applications that generate different types of workloads in order to evaluate operating system behaviour under varying conditions in later performance testing phases. By using controlled and well understood tools, this phase establishes a structured foundation for analysing CPU, memory, disk I/O, and network performance.

The selected applications are chosen to reflect both synthetic stress testing and realistic service workloads, supporting a balanced evaluation of system performance and resource management trade-offs [1].

## Application selection matrix
The following table presents the selected applications, the workload types they represent, and the reason for their inclusion in the performance evaluation plan.

| Application | Workload Type | Purpose | Justification |
|------------|--------------|---------|---------------|
| stress-ng | CPU-intensive | Generate sustained processor load | Widely used stress-testing tool that allows controlled CPU workload generation |
| stress-ng | Memory-intensive | Simulate high memory pressure | Enables observation of memory allocation, caching, and potential swapping behaviour |
| dd | Disk / I/O-intensive | Perform sequential read/write operations | Simple and reliable utility for stressing disk throughput and identifying I/O bottlenecks |
| iperf3 | Network-intensive | Measure network throughput and latency | Standard benchmarking tool for analysing network performance between systems |
| nginx | Server workload | Simulate a lightweight production server | Represents a realistic service workload combining CPU, memory, and network usage |

The use of both syntetic benchmarks and a server-style application ensures that performance testing captures both isolated resource stress and integrated system behaviour [1], [2].

## Installation Documentation
The selected applications will be installed on the server system using the Advanced Package Tool (APT), executed remotely via SSH from the workstation. The following commands will be used during the installation phase:



sudo apt update

sudo apt install stress-ng

sudo apt install iperf3

sudo apt install nginx



The dd utility is included by default within the Linux core utilities and does not require additional installation.

## Expected Resource Profiles
Prior to executing performance tests, the expected resource behaviour of each application has been identified based on its workload characteristics.
- CPU-intensive workload (stress-ng)

Expected to significantly increase CPU utilisation and system load averages, allowing analysis of processor scheduling and saturation effects.
- Memory-intensive workload (stress-ng)

Expected to consume a substancial portion of available RAM, enabling observation of memory pressure, caching behaviour, and potential swap usage.
- Disk I/O workload (dd)

Expected to generate sustained disk read or write activity, highlighting storage throughput limitations and I/O performance characteristics.
- Network workload (iperf3)

Expected to increase network traffic between the server and workstation, allowing measurment of throughput and latency under controlled conditions.
- Server workload (nginx)

Expected to produce moderate, continuous resource usage across CPU, memory, and network interfaces, representing a realistic service deployment scenario.

Defining expected behaviour prior to testing supports structured analysis and enables meaningful comparison between observed results and theoretical expectations [1].

## Monitoring Strategy
System performance during workload execurtion will be monitored remotely from the workstation using SSH and native Linux command-line tools defined in the previous phase's performance testing plan. Metrics such as CPU load, memory usage, disk utilisation, and network activity will be observed in real time during baseline and workload execution phases.

Using standard command-line monitoring tools ensures minimal system overhead and maintains consistency with headless server administration practices commonly used in professional environments [2], [3].
## Reference list
1. M. Nemeth, E. Snyder, T. Hein, B. Whaley, and D. Mackin, UNIX and Linux System Administration Handbook, 5th ed. Pearson, 2018.

2. W. Shotts, The Linux Command Line, 2nd ed. No Starch Press, 2019.

3. Canonical Ltd., “Ubuntu Server Guide – Performance and Monitoring.” [Online]. Available: https://ubuntu.com/server/docs
. [Accessed: 21-Dec-2025].
