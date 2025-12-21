# Security planning and testing methodology
## Performance testing plan
### Objectives
The objective for devising performance testing plan is to define structured plan for testing operating system's performance under various workload conditions in later phases of this assignment.

### Monitoring Architecture
Performance monitoring will be conducted remotely from the workstation system using Secure Shell (SSH). All monitoring commands will be executed on the server through SSH sessions initiated from the workstation. This approach reflects professional system administration practices, where production servers are typically managed remotely without direct console or graphical access [1]

The server operates in a headless configuration with no desktop environment installed. Monitoring relies exclusively on native command-line utilities available in the base Linux installation, avoiding unnecessary software installations that could increase system overhead or expand the attack surface [1], [2].

### Metrics to be monitored
The following performance metrics have been selected to provide a comprehensive view of system behaviour:

#### 1. CPU utilisation

Used to analyse processor load, task scheduling, and the impact of CPU-intensive workloads.


#### 2. Memory usage

Used to observe RAM consumption, caching behaviour, and potential memory pressure.


#### 3. Disk I/O activity

Used to evaluate filesystem performance, read/write behaviour, and storage bottlenecks.


#### 4. Network performance

Used to measure latency, throughput, and the impact of network-intensive workloads.


These metrics align with standard operating system performance evaluation practices and provide the necessary data for identifying bottlenecks and optimisation opportunities in later phases [1].

### Monitoring Tools and Data Collection
Monitoring will be performed native Linux command-line utilities, including but not limited to:

- 'top' and 'uptime' for CPU load and system activity

- 'free' for memory usage

- 'df' for disk utilisation

- 'ip' and related networking tools for interface and traffic inspection

  All commands will be executed remotely via SSH, ensuring consistency with real-world remote administration workflows and reinforcing command-line proficiency [2], [4].

  Where appropriate, monitoring commands may be executed repeatedly or scripted in later phases to enable consistent data collection across multiple testing scenarios.

### Planned Testing Methodology
Performance evaluation in later phases will follow a structured methodology consisting of:

#### 1. Baseline measurement
Capturing system performance under minimal load to establish reference values.

#### 2. Workload execution
Running selected applications representing different workload types (e.g., CPU-intensive, memory- intensive, I/O-intensive)

#### 3. Live monitoring
Observing system metrics during workload execution using the defined monitoring tools.

#### 4. Post-test analysis
Comparing results against baseline measurements to identify performance degradation, bottlenecks, and resource contention.

This approach supports controlled experimentation and enables meaningful comparison between different workload scenarios [1], [7].

### Justification of approach
This performance testing plan prioritises realism security, and minimal system impaact. Remote monitoring via SSH mirrors industry-standard server management practices and ensures that administrative tasks are performed without direct physical or graphical access to the server [4]. Using native command-line tools avoids unnecessary software dependencies and maintains a minimal, efficient server configuration [2].

## Security checklist
## Threat model table
