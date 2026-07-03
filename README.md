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

## Citing
The following information can be used when citing this dataset:

L.F. Haaijer, *DDoS Packet Capture Collection*, (2022). Available from https://github.com/StopDDoS/packet-captures


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

## Used by
Nainar, N. K., & Panda, A. (2023). Wireshark for Network Forensics Apress. https://doi.org/10.1007/978-1-4842-9001-9

Sharma, R. (2024, November 18). Analyzing a DDOS attack using Wireshark - Ronak Sharma - Medium. Medium. https://medium.com/@ronak.d.sharma111/analyzing-a-ddos-attack-using-wireshark-8535274cd00e

Shin, H., Jeong, J., Cho, K., Lee, J., Kwon, O., & Shin, D. (2025). Detection of Domain Name Server Amplification Distributed Reflection Denial of Service Attacks Using Convolutional Neural Network-Based 
Image Deep Learning. Electronics, 14(1), 76. https://doi.org/10.3390/electronics14010076

Kiechl, P. (2023). Simulator of Distributed Datasets for Pulse-wave DDoS Attacks (Master's thesis, University of Zurich). https://www.zora.uzh.ch/id/eprint/255744/1/MA_Thesis_Pascal_Kiechl.pdf

Dübendorfer, M. (2022). Distributed Analysis of Cyberattacks in a Collaborative Setting. Communication Systems Group, Department of Informatics, March. https://capuana.ifi.uzh.ch/publications/PDFs/22355_BA_Marion-Duebendorfer_16-927-501.pdf

Cavallo, S. (2023). Visualizing Cybersecurity-a comparative study toward a security visualization methodology (Doctoral dissertation, Politecnico di Torino). https://webthesis.biblio.polito.it/27656/1/tesi.pdf

Archilla, David Ramos. (2024) Diseño e implementación de un sistema de detección y gestión de ataques de Denegación de Servicio en redes aplicando técnicas de inteligencia artificial https://oa.upm.es/79025/1/TFG_DAVID_RAMOS_ARCHILLA.pdf

DDoS attack classification mechanism using split window strategy and lstm model https://ir.lib.cyut.edu.tw/bitstream/310901800/42578/1/111CYUT0652017-004.pdf

Yunpeng Tan, Qingyang Li, Mingxin Yang, and Xinggong Zhang. 2026. DTAC: Decision-Tree-based Automatic Configuration of Entangled DDoS Defense Policies. In Proceedings of the 19th European Workshop on Systems Security (EuroSec '26). Association for Computing Machinery, New York, NY, USA, 98–104. https://doi.org/10.1145/3803525.3804985

Falter, C. (2023). Emulator for Distributed DDoS Datasets (EDDD) (Master's thesis, University of Zurich). https://www.zora.uzh.ch/id/eprint/255747/1/MA_Calvin_Falter.pdf

Strelciuc R. Intelligent DDoS Mitigation at the Autonomous System Edge: sFlow and Remote Triggered Black Holes in BGP Networks. https://digikogu.taltech.ee/en/Download/59a3423c-66b2-4397-b6f8-e31aaeccec24

de Castro, E. M. P. (2024). Security Data Analytics in 6G Open Networks. https://optaresolutions.com/wp-content/uploads/2025/11/Thesis_Security-Data-Analytics-in-6G-Open-Networks_Eva-Miriam-Pires-de-Castro.pdf

S. Pullagura, N. Pandita, A. Kakwani, S. A. Gowda and K. K. Rajamani, "SmartGuard: A Machine Learning Based Classification Framework for Automated DoS/DDoS Defense in Next-Generation Firewall Systems," 2026 IEEE 18th International Conference on Advanced Trends in Radioelectronics, Telecommunications and Computer Engineering (TCSET), Lviv, Ukraine, 2026, pp. 1-6, doi: 10.1109/TCSET65181.2026.11461164.

Vedula, Vasudha, Rajendra V. Boppana, and Palden Lama. "Attack-Specific Feature Construction to Detect Malicious TCP Flows." 2024 IEEE International Conference on Cyber Security and Resilience (CSR). IEEE, 2024. https://ieeexplore.ieee.org/abstract/document/10679441/

PATOVÁ, PRÁCE Bc PAVLÍNA, and JAN KUČERA. "PROSTŘEDÍ PRO TESTOVÁNÍ ALGORITMŮ POTLA-ČENÍ ÚTOKŮ DDOS." https://theses.cz/id/h9ej7b/xpatov00.pdf

Tang, Dan, et al. "DNSGreen: A Comprehensive Defense System against Bounce-style DNS DDoS attacks with P4." IEEE Transactions on Computers (2025). https://ieeexplore.ieee.org/abstract/document/11230647

Huang, Xiaojun. Detecting Amplification DDoS Attacks in Multi-Cloud Environments. Diss. School of Computing, University of Portsmouth. https://pure.port.ac.uk/ws/portalfiles/portal/122445547/UP758038-Xiaojun_Huang-PhD_Thesis_19_May_2026.pdf

Vedula, Vasudha. Robust Techniques to Detect and Mitigate Volumetric and Non-Volumetric Network Attacks. Diss. The University of Texas at San Antonio, 2024.

