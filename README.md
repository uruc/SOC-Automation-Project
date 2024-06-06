# SOC Automation Lab

**Author: [Uruc Tarim](https://github.com/uruc)**

## Introduction

### Overview
The SOC Automation Project aims to create an automated Security Operations Center (SOC) workflow that streamlines event monitoring, alerting, and incident response. By leveraging tools such as Wazuh, Shuffle, and TheHive, this project will enhance the efficiency and effectiveness of SOC operations. The project involves setting up a Windows 10 client with Sysmon for event generation, Wazuh for event management and alerting, Shuffle for automation, and TheHive for case management and response actions.

![SOC Automation Diagram](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/SOC_Automation_Diagram.png)

### Purpose and Goals
- **Automate Event Collection and Analysis:** Ensure security events are collected and analyzed in real-time with minimal manual intervention.
- **Streamline Alerting Process:** Automate the process of generating and forwarding alerts to relevant systems and personnel.
- **Enhance Incident Response Capabilities:** Automate responsive actions to security incidents, improving reaction time and effectiveness.
- **Improve SOC Efficiency:** Reduce the workload on SOC analysts by automating routine tasks, allowing them to focus on critical issues.

## Prerequisites

### Hardware Requirements
- A host machine capable of running multiple virtual machines.
- Sufficient CPU, RAM, and disk space to support the VMs and their operations.

### Software Requirements
- **VMware Workstation/Fusion:** For creating and managing virtual machines.
- **Windows 10:** As the client machine for generating security events.
- **Ubuntu 22.04:** For deploying Wazuh and TheHive.
- **Sysmon:** Installed on Windows 10 for detailed event logging.

### Tools and Platforms
- **Wazuh:** An open-source security monitoring platform that will serve as the central point for event collection, analysis, and alerting.
- **Shuffle:** A security automation platform that will handle the workflow automation for alert processing and response actions.
- **TheHive:** A scalable, open-source Security Incident Response Platform designed for SOCs to efficiently manage and resolve incidents.
- **VirusTotal:** An online service that analyzes files and URLs to detect viruses, worms, trojans, and other kinds of malicious content.
- **Cloud Services or Additional VMs:** Wazuh and TheHive can be deployed either on cloud infrastructure or additional virtual machines depending on your resources and preferences.

### Prior Knowledge
- **Basic Understanding of Virtual Machines:** Familiarity with setting up and managing VMs using VMware.
- **Basic Linux Command Line Skills:** Ability to perform basic tasks in a Linux environment, such as installing software and configuring services.
- **Knowledge of Security Operations and Tools:** Understanding of security monitoring, event logging, and incident response concepts.

## Setup

### Step 1: Install and Configure Windows 10 with Sysmon

1. **Install Windows 10 on VMware:**
   ![Windows 10 Installation](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/Pasted%20image%2020240603131110.png)

2. **Install Sysmon:**
   ![Sysmon Installation](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/Pasted%20image%2020240603131150.png)

3. **Download Sysmon configuration files from [Sysmon Modular Config](https://github.com/olafhartong/sysmon-modular):**
   ![Sysmon Modular Config](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/Pasted%20image%2020240603131815.png)
   ![Sysmon Modular Config Files](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/Pasted%20image%2020240603132002.png)

4. **Extract the Sysmon zip file and open PowerShell as an administrator. Navigate to the Sysmon directory extracted from the zip file:**
   ![Extract Sysmon Zip](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/Pasted%20image%2020240603133020.png)

5. **Place the Sysmon configuration file into the Sysmon directory as well.**

6. **Before installing Sysmon, check if it is already installed on the Windows machine by verifying:**
   - Services
   - Event Viewer > Applications and Services Logs > Microsoft > Windows

   ![Check Sysmon Installation](https://github.com/uruc/SOC-Automation-Lab/blob/main/images/Pasted%20image%2020240603133433.png)

7. **Since Sysmon is not installed, proceed with the installation using the command:**

