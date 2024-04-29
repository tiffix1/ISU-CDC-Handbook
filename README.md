# ISU CDC Handbook
### Guides, tutorials, and reference material to help you prepare and conquer the Cyber Defense Competition at Iowa State University.
---
# Table of Contents
- [What to Expect](#what-to-expect)
  - [What is the CDC](#what-is-the-cdc)
  - [Rules of Engagement](#rules-of-engagement)
  - [Scenarios and Anomalies](#scenarios-and-anomalies)
  - [Red team, Fire Drills, and Social Engineering](#red-team-fire-drills-and-social-engineering)
  - [Competition Network and Environment](#competition-network-and-environment)
- [Before the Competition](#before-the-competition)
  - [Team Formation and Registration](#team-formation-and-registration)
  - [Planning a Playbook and Basic Triaging](#planning-a-playbook-and-basic-triaging)
  - [Creating a Practice Network](#creating-a-practice-network)
  - [What to Practice](#what-to-practice)
- [Preparing for the Competition](#preparing-for-the-competition)
  - [Scanning for vulnerabilities](#scanning-for-vulnerabilities)
  - [Changing Default Passwords](#changing-default-passwords)
  - [Configuring Active Directory](#configuring-active-directory)
  - [Configuring a Database](#configuring-a-database)
  - [Configuring a Firewall](#configuring-a-firewall)
  - [Configuring VLAN](#configuring-vlan)
  - [Configuring an Intrusion Detection System](#configuring-an-intrusion-detection-system)
  - [Port Scanning](#port-scanning)
  - [System Hardening  for Linux](#system-hardening-for-linux)
  - [System Hardening for Windows](#system-hardening-for-windows)
  - [System Hardening for Custom Applications](#system-hardening-for-custom-applications)
- [Attack Phase of the Competition](#attack-phase-of-the-competition)
  - [Signs of an Attack](#signs-of-an-attack)
  - [Sniffing Network Traffic](#sniffing-network-traffic)
  - [Understanding Windows Event Viewer](#understanding-windows-event-viewer)
  - [Analyzing logs](#analyzing-logs)
  - [Identifying Malicious Processes](#identifying-malicious-processes)
  - [Isolating an Affected Machine](#isolating-an-affected-machine)
  - 
---   

# What to Expect

## What is the CDC
## Rules of Engagement
## Scenarios and Anomalies
## Red Team, Fire Drills, and Social Engineering
## Competition Network and Environment
---
# Before the Competition

## Team Formation and Registration
## Planning a Playbook and Basic Triaging
## Creating a Practice Network
Practice makes perfect and nothing beats having your very own network to test out what you'll learn. Before you get started you will need to download a few applications; a hyper visor and an ISO file. A hypervisor is the platform that will run your virtualized network enviroment and an ISO file is often the format of choice for distributing operating systems. Below are some resources to get started, check with your school as some insitutions offer vmware or windows license to students for free.
1. Install hypervisor of your choice
   For this example we will be using Vmware Workstation since the competition uses Vmware products to host the virtual network. Simply navigate to the download link, and follow the wizard for installation
   - [Vmware Workstation](https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html.html.html)  &nbsp;  <img src="https://static.wikia.nocookie.net/logopedia/images/6/62/VMware_Workstation_7_logo.png/revision/latest?cb=20140525014047" width="40" height="40">
     -  30 day free trial
        <br>
        
   - [VirtualBox](https://www.virtualbox.org/wiki/Downloads) &nbsp; <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Virtualbox_logo.png/330px-Virtualbox_logo.png" width="50" height="50">
     -  Free
      
   - [HyperV](https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v) &nbsp; <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Windows_logo_-_2012.svg/2048px-Windows_logo_-_2012.svg.png" width="40" height="40">
     - Windows license required

2. Download ISO files 
    The CDCs scenarios vary but most CDCs have an Active Directory server, a Database,

   Essentials:
    - Ubuntu:
      - [Server ISO Download](https://ubuntu.com/download/alternative-downloads#other-images-and-mirrors)
      - [Desktop ISO Download](https://ubuntu.com/download/alternative-downloads)
    - Windows:
      - [Windows Server 2016 Evaluation ISO Download](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2016)
      - [Windows 10 Evaluation ISO Download](https://info.microsoft.com/ww-landing-windows-10-enterprise.html) (Requires registration)
      
   Additional:
    - Alma
      - [ISO Download](https://mirrors.almalinux.org/isos.html)
    - Pfsense
      - [ISO Download](https://www.pfsense.org/download/)
    - Kali
      - [ISO Download](https://www.kali.org/get-kali/#kali-installer-images)
    - Security Onion
      - [ISO Download](https://download.securityonion.net/file/securityonion/securityonion-2.4.60-20240320.iso)
              <br>
      <br>

4. Create Virtual Machines
      <br>
Open Workstation and navigate to "File > New Virtual Machine" or click "ctrl + N"
  <img src="https://i.imgur.com/mHI6E7e.png">
  Select typical and click "Next"
  <img src="https://i.imgur.com/13YSA4M.png">
  Click browse and select the ISO file you downloaded
  <img src="https://i.imgur.com/mJgeZDf.png">
  Navigate through the wizard by creating a user account and appropriately name the host
  <img src="https://i.imgur.com/2v063EI.png">
  The default 20 GB should be enough for your machine
  <img src="https://i.imgur.com/Mb2hSO1.png">
   Confirm all the information is correct and click "finish"
  <img src="https://i.imgur.com/pSxO2aT.png">
  
## What to Practice
---
# Preparing for the Competition

## Scanning for Vulnerabilities
## Changing Default Passwords
## Configuring Active Directory
## Configuring a Database
## Configuring a Firewall
## Configuring VLAN
## Configuring an Intrusion Detection System
## Port Scanning
## System Hardening for Linux
## System Hardening for Windows
## System Hardening for Custom Applications
---
# Attack Phase of the Competition
## Signs of an Attack
## Sniffing Network Traffic
## Understanding Windows Event Viewer
## Analyzing logs
## Identifying Malicious Processes
## Isolating an Affected Machine



