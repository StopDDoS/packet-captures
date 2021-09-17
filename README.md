# DDoS Packet Capture Collection

This is a collection of multiple anonymized packet captures of real-world and lab-tested DDoS attacks.

## Mirror
Github has disabled LFS on this repository due to the high amount of downloads. A zipped version of this repository can be downloaded at [https://wqrld.net/captures.zip](https://wqrld.net/captures.zip).

## Goal
The goal of providing these captures is to stimulate the growth of ddos research. 
Real-world DDoS captures are hard to come by which makes research harder.
We are trying to overcome that issue.


## License
These captures may be freely used to build and improve DDoS Protection systems. 
Attribution is not required, but greatly appreciated. Do not claim any of these resources as your own.


## Contributing
If these captures or any of our other resources were useful to you, or you just want to help, *Please* contribute through one of our github repositories.

Make sure that these captures only show one-way (incoming) traffic and are atleast 99% real ddos traffic 
(preferably 100%, but this may include things like icmp control messages. Please leave those in.)

If you prefer to anonymize your captures because they may contain real user information. Please do. 
Instructions are below.

## Naming scheme
This project uses a very lean naming scheme. The name should start with either amp (amplification) or pkt (spoofed/direct) and then udp/tcp/another protocol. 
For amplification, if you know what protocol is being used, please add the protocol name (eg SNMP). Otherwise please use the port. Other than that you can add any other information as long as the title stays short and identifyable. 


## Anonymizing your own packet captures
First, open your capture in wireshark and write a display filter to only select traffic that's part of your attack.
For example `udp && ip.dst == 10.10.10.10 && udp.dstport == 8080`. Then under file > export specified packets write a new filtered pcap.

(optionally, but recommended) Also anonymize the destination ip. This can for example be done with tcpreplay's tcprewrite
```bash
for file in $(ls);
  do tcprewrite --infile=$file --outfile=/root/anonymous/$file --dstipmap=0.0.0.0/0:10.10.10.10;
done
```
