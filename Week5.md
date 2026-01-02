# Advanced Security and Monitoring Ifrastructure
## Mandatory Access Control with AppArmor
To extend system security beyond traditional discretionary access controls, mandatory access control (MAC) was enforced using AppArmor, which is enabled by default on Ubuntu Server. AppArmor restricts application capabilities through predefined security profiles, limiting the potential damage caused by compromised services or misbehaving processes [1][4].

The service status and profile enforcement mode were verified to ensure that AppArmor was actively protecting the system rather than operating in a passive state (Figures 1 and 2)

![Figure 1. Evidence showing AppArmor service is active](images/Phase5/Figure1.png)

Figure 1. Evidence showing AppArmor service is active.

![Figure 2. Evidence confirming loaded profiles and enforcing mode.](images/Phase5/Figure2.png)

Figure 2. Figure 2. Evidence confirming loaded profiles and enforcing mode.

## Automated Security Updates
To ensure timely application of security patches, automatic security updates were configured. This reduces exposure to known vulnerabilities by ensuring that critical updates are installed without manual intervention, aligning with industry best practices for server maintenance [1][4].

The unattended-upgrades package was installed and enabled (Figure 3), and configuration files were reviewed to confirm that security repositories were included (Figure 4)

![Figure 3. Evidence showing unattended-upgrades configuration prompt.](images/Phase5/Figure3.png)

Figure 3. Evidence showing unattended-upgrades configuration prompt.

![Figure 4. Evidence confirming automatic security updates are enabled.](images/Phase5/Figure4.png)

Figure 4. Evidence confirming automatic security updates are enabled.

## Intrusion Prevention with Fail2Ban
