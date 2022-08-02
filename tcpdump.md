all the filters/options for tcpdump

-i any – Listen on all interfaces just to see if you’re seeing any traffic.

-D – Show the list of available interfaces

-w – Write packets to a file.

-r – Read packets from a file.

-n – Don’t resolve hostnames.

-nn – Don’t resolve hostnames or port names.

-tttt – Human readable timestamp output.

-X – Show the packet’s contents in both hex and ASCII.

-A – Show the packet’s contents in ASCII.

-v, -vv, -vvv – Increase the amount of packet information you get back.

-c – Only get x number of packets and then stop.

-s – Define the snapshot length, or the size of the capture in bytes. Use -s0 to get everything.

-S – Print absolute sequence numbers.

-e – Get the ethernet header as well.

-q – Show less verbose output.

-E – Decrypt IPSEC traffic by providing an encryption key.

It is also possible to pipe to additional commands. So if you want to see a specific keyword, do the following:

sudo tcpdump -lA port http | grep cnn.com

One of the most common recent Linux attacks is the Shellshock exploit. To see this you can use the following:

sudo tcpdump -vvnnAls0 http |grep -i -A5 -B5 ‘user-agent: () { :; };’

