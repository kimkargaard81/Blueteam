Volatility can be found here: https://github.com/volatilityfoundation/volatility
On Kali, run python vol.py -f ... (see below). 
Command List
volatility -f memdump.mem imageinfo // Take memory image “memdump.mem” and determine the suggested profile for analysis. The profile is the operating system, version, and architecture.

volatility -f memdump.mem --profile=PROFILE pslist // Take memory image, provide the profile, then use the pslist plugin to print a list of processes to the terminal.

volatility -f memdump.mem --profile=PROFILE pstree // Use the pstree plugin to print a process tree to the terminal.

volatility -f memdump.mem --profile=PROFILE psscan // Use the psscan plugin to print all available processes, including hidden ones often used by malware (compare this to pslist to see if there’s any differences!).

volatility -f memdump.mem --profile=PROFILE psxview // Use the plugin psxview plugin to print expected and hidden processes. This is a combination of pslist and psscan plugins.

volatility -f memdump.mem --profile=PROFILE netscan // Use the plugin netscan to identify any active or closed network connections.

volatility -f memdump.mem --profile=PROFILE timeliner // Use the timeliner plugin to create a timeline of events from the memory image.

volatility -f memdump.mem --profile=PROFILE iehistory // Use the iehistory plugin to pull internet browsing history.

volatility -f memdump.mem --profile=PROFILE filescan // Use the filescan plugin to identify any files on the system from the memory image.

volatility -f memdump.mem --profile=PROFILE dumpfiles -n --dump-dir=./ // Use the dumpfiles plugin to retrieve files from the memory image. In this case our terminal is open in the Desktop (root@SBTLab2:~/Desktop) and we are using the output location ./ which tells Volatility to put the files in our current location, the Desktop.

Additional Resources
If you want to get some practice in before the exercise, or if you’ve finished the exercise and want to play around with Volatility some more, you are able to download open-source memory dumps at Volatility’s own GitHub link, all created for analysis with Volatility. We strongly suggest that students try at least a few of these dumps to see if they can find anything interesting and become more confident using this tool.
https://github.com/volatilityfoundation/volatility/wiki/Memory-Samples

You can find a great list of useful Volatility commands here:
https://book.hacktricks.xyz/forensics/volatility-examples#list-processes
