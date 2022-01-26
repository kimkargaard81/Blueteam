https://mitre-attack.github.io/attack-navigator/

MITRE ATT&CK provides an overview of the techniques used by various APTs and one can use the Attack Navigator to outline the different phases used by a specific APT. 

The different phases of MITRE ATT&CK are:

1. Initial Access

Currently 9 techniques for initial access:

        Drive-by Compromise
        Exploit public-facing application
        External remote services
        Hardware additions
        Phishing
        Replication through removable media
        Supply chain compromise
        Trusted relationship
        Valid accounts

2. Execution

These techniques are used to describe ways that adversaries will execute malicious code for a number of purposes, and at the time of writing currently includes 12 top-level techniques.
 
        Command and Scripting Interpreter
        Container Administration Command
        Deploy Container
        Exploitation for Client Execution
        Inter-Process Communication
        Native API
        Scheduled Task/Job
        Shared Modules
        Software Deployment Tools
        System Services
        User Execution
        Windows Management Instrumentation

Persistence

Once an adversary has access to a system they need to attempt to maintain their foothold by hiding from the defenders and utilising multiple methods to regain access to the compromised host. At the time of writing there are currently 19 high-level techniques for this category. 

        Account Manipulation
        BITS jobs
        Boots or Logon Autostart Execution
        Boot or Logon Initialisation Scripts
        Browser Extensions
        Compromise Client Software Binary
        Create Account
        Create or Modify System Process
        Event Triggered Execution
        External Remote Services
        Hijack Execution Flow
        Implant Internal Image
        Modify Authentication Process
        Office Application Startup
        Pre-OS Boot
        Scheduled Task/Job
        Server Software Component
        Traffic Signaling
        Valid Accounts
        
Privilege Escalation

These techniques are used to describe ways that adversaries will attempt to gain higher privileges, such as moving from a standard user to an administrator, or from an admin to a domain admin. At the time of writing currently includes 13 top-level techniques. 
       
        Abuse Elevation Control Mechanism
        Access Token Manipulation
        Boot or Logon Autostart Manipulation
        Boot or Logon Inilisation Scripts
        Create or Modify System Process
        Domain Policy Modification
        Escape to Host
        Event Triggered Execution
        Exploitation for Privilege Escalation
        Hijack Execution Flow
        Process Injection
        Schedule Task/Job
        Valid Accounts

Defense Evasion

These techniques are used to describe ways that adversaries will work to evade or disable security defenses such as antivirus, endpoint detection and response, logging, and human analysts to ensure they can remain in the network for as long as possible. At the time of writing this stage currently includes a crazy 38 top-level techniques!

        Abuse Elevation Control Mechanism
        Access Token Manipulation
        BITS Jobs
        Build Image on Host
        Deobfuscate/Decode Files or Information
        Deploy Container
        Direct Volume Access
        Domain Policy Modification
        Execution Guardrails
        Exploitation for Defense Evasion
        File and Directory Permission Modification
        Hide Artifacts
        Hijack Execution Flow
        Impair Defenses
        Indicator Removal on Host
        Indirect Command Execution
        Masquerading
        Modify Authentication Process
        Modify Cloud Compute Infrastructure
        Modify Registry
        Modify System Image
        Network Boundary Bridging
        Obfuscated Files or Information
        Pre-OS Boot
        Process Injection
        Reflective Code Loading
        Rogue Domain Controller
        Rootkit
        Signed Binary Proxy Execution
        Signed Script Proxy Execution
        Subvert Trust Controls
        Template Injection
        Traffic Signaling
        Trusted Developer Utilities Proxy Execution
        Unused/Unsupported Cloud Regions
        Use Alternate Authentication Material
        Valid Accounts
        Virtualsation/Sandbox Evasion
        Weaken Encryption
        XSL Script Processing
        

Credential Access

These techniques are used to describe ways that adversaries will work to steal credentials such as passwords and usernames from compromised systems using methods such as credential dumping (retrieving credentials that are stored in memory while the system is powered on) or deploying a key logger to monitor what keyboard buttons are pressed. At the time of writing this category currently includes 15 top-level techniques. 

        Adversary-In-The-Middle
        Brute Force
        Credentials from Password Stores
        Exploitation for Credential Access
        Forced Authentication
        Forge Web Credentials
        Input Capture
        Modify Authentication Process
        Network Sniffing
        OS Credential Dumping
        Steal Application Access Token
        Steal or Forge Kerberos Tickets
        Steal Web Session Cookie
        Two Factor Authentication Interception
        Unsecured Credentials

Discovery

These techniques are used to describe ways that adversaries will collect more information about the network they’re in and other systems that are present. Adversaries should spend a good deal of time at this stage, quietly watching what is happening around them so they can take further actions and ensure that they remain stealthy, attempting to blend in to ‘normal’ network activity. At the time of writing currently includes 29 top-level techniques. 

        Account Discovery
        Application Window Discovery
        Browser Bookmark Discovery
        Cloud Infrastructure Discovery
        Cloud Service Dashboard
        Cloud Service Discovery
        Cloud Storage Object Discovery
        Container and Resource Discovery
        Domain Trust Discovery
        File and Directory Discovery
        Group Policy Discovery
        Network Service Scanning
        Network Share Discovery
        Network Sniffing
        Password Policy Discovery
        Peripheral Device Discovery
        Permission Groups Discovery
        Process Discovery
        Query Registry
        Remote System Discovery
        Software Discovery
        System Information Discovery
        System Location Discovery
        System Network Information Discovery
        System Owner/User Discovery
        System Service Discovery
        System Time Discovery
        Virtualisation/Sandbox Evasion
        
Lateral Movement

An adversary commonly has to exploit multiple machines within a network to reach their primary objective, the movement between these hosts is called ‘Lateral movement’. At the time of writing this there are currently 9 techniques mapped to Lateral Movement.

        Exploitation of Remote Services
        Internal Spearphishing
        Lateral Tool Transfer
        Remote Service Session Hijacking
        Remote Services
        Replication Through Removable Media
        Software Deployment Tools
        Taint Shared Content
        Use Alternate Authentication Material
       

Collection

These techniques are used to describe ways that adversaries will identify important files or information, collect them, and prepare them for data exfiltration. At the time of writing currently includes 17 top-level techniques.

        Adversary-In-The-Middle
        Archive Collected Data
        Audio Capture
        Automated Collection
        Browser Session Hijacking
        Clipboard Data
        Data From Cloud Storage Object
        Data From Configuration Repository
        Data From Information Repositories
        Data From Local System
        Data From Network Shared Drive
        Data From Removable Media
        Data Staged
        Email Collection
        Input Capture
        Screen Capture
        Video Capture

Command and Control

 Command and Control consist of techniques and methods adversaries use to communicate with systems they have compromised on the targets networks. Adversaries use various methods of command and control and will use commonly used protocols and ports to blend in with normal traffic, making malicious traffic harder to identify. At the time of writing there are a total of 16 techniques for Command and Control. 

        Application Layer Protocol
        Communication Through Removable Media
        Data Encoding
        Data Obfuscation
        Dynamic Resolution
        Encrypted Channel
        Fallback Channels
        Ingress Tool Transfer
        Multi-Stage Channels
        Non-Application Layer Protocol
        Non-Standard Port
        Protocol Tunneling
        Proxy
        Remote Access Software
        Traffic Signaling
        Web Service

Exfiltration

At some point an adversary needs to fulfil their objectives, quite often this could be to steal valuable data. These actions are referred to as exfiltration and is the tenth phase within MITRE. The Exfiltration phase consists of techniques used to steal data from the compromised network and systems, and ways of avoiding detection when completing this. This can include the compression, encryption or encoding of files when removing them from the network and typically involves transferring it over a command-and-control communication channel. Exfiltration has 9 techniques at the time of writing.

        Automated Exfiltration
        Data Transfer Size Limits
        Exfiltration Over Alternative Protocol
        Exfiltration Over C2 Channel
        Exfiltration Over Other Network Medium
        Exfiltration Over Physical Medium
        Exfiltration Over Web Service
        Scheduled Transfers
        Transfer Data to Cloud Account

Impact

 These techniques are used to describe the actions that adversaries may use to disrupt availability or compromise integrity by manipulating business and operational processes, such as tampering or destroying data. At the time of writing currently includes 13 top-level techniques. 
 
        Account Access Removal
        Data Destruction
        Data Encrypted for Impact
        Data Manipulation
        Defacement
        Disk Wipe
        Endpoint Denial of Service
        Firmware Corruption
        Inhibit System Recovery
        Network Denial of Service
        Resource Hijacking
        Service Stop
        System Shutdown/Reboot
 

