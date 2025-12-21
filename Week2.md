# Security planning and testing methodology
## Performance testing plan
### Objectives
The objective for devising performance testing plan is to define structured plan for testing operating system's performance under various workload conditions in later phases of this assignment.

### Monitoring Architecture
Performance monitoring will be conducted remotely from the workstation system using Secure Shell (SSH). All monitoring commands will be executed on the server through SSH sessions initiated from the workstation. This approach reflects professional system administration practices, where production servers are typically managed remotely without direct console or graphical access [1]

The server operates in a headless configuration with no desktop environment installed. Monitoring relies exclusively on native command-line utilities available in the base Linux installation, avoiding unnecessary software installations that could increase system overhead or expand the attack surface [1], [2].

### Metrics to be monitored
The following performance metrics have been selected to provide a comprehensive view of system behaviour:

1. CPU utilisation

Used to analyse processor load, task scheduling, and the impact of CPU-intensive workloads.


2. Memory usage

Used to observe RAM consumption, caching behaviour, and potential memory pressure.


3. Disk I/O activity

Used to evaluate filesystem performance, read/write behaviour, and storage bottlenecks.


4. Network performance

Used to measure latency, throughput, and the impact of network-intensive workloads.


These metrics align with standard operating system performance evaluation practices and provide the necessary data for identifying bottlenecks and optimisation opportunities in later phases [1].

### Monitoring Tools and Data Collection

## Security checklist
## Threat model table
