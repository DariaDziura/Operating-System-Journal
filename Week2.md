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

## Security configuration checklist
### Objective
This security configuration checklist defines the planned baseline security controls to be implemented on the server system in later phases of the coursework. The pupose of this checklist is to demonstrate an understanding of operating system security principles and to ensure that security controls are applied systematically rather than reactively.

At this stage, no security configurations are implemented; the checklist serves as a designn and reference for subsequent phases.

### Planned Security controls
#### 1. Secure Remote Access (SSH)
- SSH will be used as the sole administrative access method to the server
- Key-based authentication will be enforced to eliminate password-based login risks
- Root login over SSH will be disabled to reduce the impact of credetial compromise
- Password authentication will be disabled once key-based access is confirmed
- SSH configuration will be reviewed and hardened to align with industry best practices for remote system administration [4].

#### 2. Firewall configuration
- A host-based firewall will be enabled on the server
- A default deny policy will be applied to incomming connections
- SSH access will be explicitly permitted only from the designated workstation IP address
- All unnecessary ports and services will remain closed to eliminate the attack surface
- Firewall rules will be documented and verified to ensure correctness and persistence accross reboots

#### 3. User and Privilege Management
- A dedicated non-root administrative user will be created for system management
- Administative privileges will be granted using sudo, adhering to the principle of least privilege
- Direct root access will be avoided for routine administration tasks
- User permissions will be reviewed to ensure that access rights are limited to what is strictly required [5]

#### 4. Mandatory Access Control (MAC)
- Mandatory Access Control will be enforced using AppArmor, which is enabled by default on Ubuntu systems
- AppArmor profiles will be reviewed to ensure they are active and enforcing restrictions on key services
- MAC controls will provide an additional layer of defence beyond traditional discretionary permissions, helping to contain potential compromises [6]

#### 5. Automatic Security Updates
- Automatic installation of security updates will be enabled to ensure timely patching of known vulnerabilities
- Update configuration will prioritise security-related packages while minimising operational disruption
- The update mmechanism will be verified to ensure it operates without requiring manual intervention [5]

#### 6. Network Security and Isolation
- The server and workstation will operate within an isolated virtual network environment
- Network exposure will be limited to required services only
- Network configuration will be documented to ensure clarity and reproducibility
- Any future network configuration changes will be evaluated for security impact before implementation

### Checklist Usage in Later Phases
This checklist will be used as verification reference during security implementation and ausiting phases. Each item will be validated through configuration inspection, command-line evidence, and testing to confirm correct application.

By defining security controls in advance, this approach supports structured security implementation, reduces configuration errors, and aligns with recognised security best parctice [5].
## Threat model table
| Threat | Description | Mitigation Strategy |
|-------|-------------|---------------------|
| Brute-force SSH attacks | Automated attempts to gain unauthorised access to the server via the SSH service | Enforce key-based authentication, disable password login, restrict SSH access via firewall, deploy intrusion detection mechanisms |
| Privilege escalation | An attacker gains elevated privileges after initial access, potentially compromising the entire system | Disable root SSH login, use non-root administrative accounts, enforce least privilege via sudo |
| Unnecessary exposed services | Additional running services increase the attack surface and potential vulnerabilities | Minimise installed services, restrict open ports using firewall rules, regularly audit active services |


The identified threats and mitigation strategies are based on common attack vectors and established security best practices [5], [7], [8].
