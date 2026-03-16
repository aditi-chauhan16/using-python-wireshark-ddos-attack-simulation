# DDoS Traffic Analysis using Python and Wireshark

## Overview
This project demonstrates the analysis of network traffic patterns related to Denial of Service (DoS) attacks using Python and Wireshark.  
The experiment was conducted in a controlled lab environment using Kali Linux.

Python scripts were used to generate test TCP and UDP packets using the Scapy library.  
Wireshark was then used to capture and analyze the network traffic.

This project helps in understanding how abnormal traffic patterns appear during DoS attacks.

---

## Tools and Technologies
- Kali Linux (Virtual Machine)
- Python 3
- Scapy Library
- Wireshark Packet Analyzer

---

## Experiment 1: TCP SYN Flood Traffic Analysis

### Objective
To generate TCP SYN packets using Python and analyze them using Wireshark.

### Method
A Python script was created using the Scapy library to generate multiple TCP SYN packets directed to port 80 of the localhost system.

Wireshark captured the packets using the loopback interface.

### Wireshark Filter Used
tcp.flags.syn == 1 && tcp.flags.ack == 0

### Observation
- Large number of SYN packets observed
- SYN flag set without ACK
- Multiple connection initiation requests

### Result
This packet pattern resembles a SYN flood attack where numerous TCP connection requests are generated.

---

## Experiment 2: UDP Flood Traffic Analysis

### Objective
To generate UDP packets and observe the traffic behavior using Wireshark.

### Method
A Python script was used to generate UDP packets with random source and destination ports.

### Wireshark Filter Used
udp

### Observation
- Large number of UDP packets captured
- Random source and destination ports
- ICMP Destination Unreachable messages observed

### Result
The observed behavior resembles a UDP flood attack where high volumes of UDP traffic are sent to overwhelm the target system.

## Project Structure

```
ddos-analysis/
│
├── syn_test.py
├── udp_test.py
├── screenshots/
│   ├── syn_capture.png
│   ├── udp_capture.png
│   └── packet_details.png
└── README.md
```

## Conclusion
This experiment demonstrated how Python can be used to generate network traffic and how packet analysis tools like Wireshark can be used to analyze suspicious traffic patterns. Understanding these traffic patterns helps in detecting and mitigating denial-of-service attacks.

---

## Disclaimer
This project was conducted strictly in a controlled lab environment for educational purposes only. The scripts should not be used to perform attacks on real systems or networks.

---

## Author
Aditi Chauhan  
B.Tech (Computer Science)  
Network Security Lab Assignment

