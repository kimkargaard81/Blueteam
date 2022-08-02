To get PCAP files to be analysed by RITA, we need to tell Zeek to convert the PCAP to a log file so that RITA can ingest:

sudo ./zeek -r /home/ubuntu/Downloads/apt1virtuallythere_1hr.pcap local "Log::default_rotation_interval = 1 day"

we can then move the logs somewhere easier to access like the desktop. Then we tell RITA to read the logs.

rita import /home/ubuntu/Desktop/ZeekLogs BTL2Demo

the BTL2Demo is to give the logs an name within RITA.

Now we want to generate HTML reports, so we run:

sudo rita html-report

