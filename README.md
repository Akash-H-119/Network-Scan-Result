# Network-Scan-Result
This report documents the results of a TCP SYN scan conducted on the local network 192.168.1.0/24 using Nmap. The scan identified 11 active hosts out of 256 possible addresses, detalling each device's IP address, MAC/vendor Information, and any open or filtered TCP ports.

-Objective:
To identify active hosts, discover open ports/services in a local network, and validate network traffic using deep packet inspection.

Steps Performed:

1.Environment Setup:

Installed Nmap on a workstation.

Determined the LAN IP range.



2.Active Host & Port Discovery:

Ran a TCP SYN scan:

nmap -sS 192.168.1.0/24

Identified live devices and enumerated their open ports and services.

3.Packet Capture & Analysis with Wireshark:

Captured packets during the Nmap scan using Wireshark, saved as scanresult.pcap.

Key observations from the packet capture:

Visible SYN and SYN-ACK handshake patterns confirming Nmap’s stealth scan behavior.

Clear mapping of hosts responding on ports such as HTTP(80), HTTPS(443), and SSH(22).

No anomalous or malicious packets beyond the intentional scan traffic.

Applied filters like:

tcp.flags.syn==1 and tcp.flags.ack==0

to isolate initial SYN packets, verifying the scanning methodology.


4.Risk Assessment & Findings:

Mapped services to potential vulnerabilities (e.g., outdated SSH versions).

Highlighted unnecessary open ports that could be hardened or firewalled.

-Outcome:

Delivered a combined network inventory and security posture snapshot:

List of live hosts and their exposed services.

Packet-level confirmation of the Nmap results.

Recommendations for closing or securing high-risk ports.

-Tools Used:

Nmap for host discovery and port scanning.

Wireshark for packet capture, protocol analysis, and scan verification.
