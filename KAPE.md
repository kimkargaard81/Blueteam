KAPE is used to grab volatile data during an investigation. 
KAPE can be downloaded from here: https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape

Once you are ready to use KAPE, start by running:

kape.exe --msource C: --mdest %1\%computername%\ --module WinPmem 

This dumps the memory binary. 

Then, run gkape.exe for the graphical interface and grab the information.
