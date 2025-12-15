# System Planning and Distribution Selection
## Architecture
### Architecture requirements
Requirements of this assignment include a headless server without desktop environment, administered remotely through the workstation acting as an administrative access point. Regarding the workstation, following approaches are allowed: second Linux Desktop VM, my host machine with SSH client or a hybrid approach
#### Distribution Selection and Justification
Ubuntu Server was selected as the operating system for this project due to its extensive official documentation and Long-Term Support (LTS) release model. LTS releases provide predictable security updates and long-term stability, making Ubuntu Server well suited for server environments [3]. Additionally, the availability of comprehensive documentation and community resources supports effective troubleshooting and system administration during deployment and configuration [2].
#### Workstation approach choice and justification
An Ubuntu desktop virtual machine was selected as the workstation environment rather than using the host machine with SSH client. This approach allows isolation between system being under development and the host operating system. That reduces impact of potential configuration errors and security risks during deployment.
#### System Architecture Diagram
