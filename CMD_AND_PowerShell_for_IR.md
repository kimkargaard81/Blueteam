in CMD on a Windows machine (run as Admin)

ipconfig /all
Shows the IP. Hostname, DNS and MAC for the machine.

tasklist 
This command will check running processes and programs and print a list to the terminal.

wmic process get description, executablepath
This command will display running processes and the associated binary file that was executed to create the process.
Example: As the description states we are able to view running processes and the executable file that initiated them. Look just below halfway down the list and you’ll find Discord.exe on the left-hand side (process name). To the right on the same row we can see that Discord was launched from C:\Users\IEUser\AppData\Local\Discord\app-0.0.307\Discord.exe – we now have the full file path! We can use this command to identify unusual process names and identify where the executable file is so we can analyze it. Process that are running out of unusual locations such as /tmp/ and /Downloads/ are definitely worth investigating further!

net user
This command will print a list of all system users to the terminal.

net localgroup administrators
This command will list all users that are in the administrators user group.

net localgroup
This command will list all the groups

net localgroup "Remote Desktop Users"
This command lists all the users in a group that has spaces in the name.

sc query | more
This command will list all services and detailed information about each one.

netstat -ab
This command will list open ports on a system, which could show the presence of a backdoor.

In PowerShell on a Windows machine (as Admin).

Get-NetIPConfiguration
Get-NetIPAddress
Similar to ifconfig in CMD, we can use the two above commands to get network-related information from the system.

Get-LocalUser
Using the above command we can list all local users on the system.

Get-LocalUser -Name Test | select *
We can provide a specific user to the command to only get information about them. Piping ( | ) the results to a “select” with a wildcard ( * ) will give us all of the properties for the command, providing us with valuable information about the account. This can be extremely useful for us as incident responders, especially when we find local accounts that do not expire or have passwords that don’t expire.

Get-Service | Where Status -eq "Running" | Out-GridView
The above command let’s us quickly identify running services on the system. By piping ( | ) the command to Out-GridView, we are telling PowerShell to show us the results in a nice window, which is much easier to work with than outputting the results to the PowerShell window.

Get-Process | Format-Table View priority
Another great command is the ability to group running processes by their priority value. Using the above command we can see the process name, the process ID (PID), and other information, where different priority ratings are grouped into tables.

Get-Process -Id 'idhere' | Select *
We can collect specific information from a service by including the name in the command (-Name ‘namehere’) or the Id, as shown above and below. Piping to Select * provides us with all the properties.

Get-ScheduledTask
Similar to Services, Scheduled Tasks are often abused and utilized a common persistence technique. With the above command we can list tasks that are set to run after certain conditions are met.

Get-ScheduledTask -TaskName 'PutANameHere' | Select *
We can dig deeper by specifying the task we’re interested in, and retrieving all properties for it.

If adversaries utilize malicious Services for persistence as a backdoor (T1543.003) we can detect this with the following PowerShell command that identified the parent processes of listening ports presented in the output of Get-NetTCPConnection:

Get-WmiObject Win32_Service | Where-Object -Property ProcessId -In (Get-NetTCPConnection).OwningProcess | Where-Object -Property State -eq Running | Format-Table ProcessId, Name, Caption, StartMode, State, PathName

nestat allows us to see running connections: 
netstat -aon or netstat -noab

We can then use the powershell get-process cmdlet to investigate any ids that we want. 

Get-Process -Id "id nr"

if we add -FileVersionInfo at the end, we can get more info about each process. Remember that processes that are system processes will give an error when trying to get that info. 




