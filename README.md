<img width="1918" height="1022" alt="final canvas" src="https://github.com/user-attachments/assets/d4fd3172-e725-4b19-8111-13a7e25d5729" />









# Legacy-Audit-Lab
Project That Involves in sniffing packets through FortiGate in Legacy System.


Walkthrough - https://medium.com/@ralindug/legacy-audit-lab-identifying-data-exfiltration-in-unencrypted-environments-using-fortigate-437853b1642e




Recently, I designed and deployed a virtualized enterprise network perimeter using GNS3, integrating a FortiGate Next-Generation Firewall and Cisco routing infrastructure. But instead of just testing connectivity, I put on my Red Team hat to audit the internal traffic.

The Architecture (Blue Team):

Deployed a FortiGate VM to act as the primary security gateway.

Configured multi-zone routing, NAT, and internal/external firewall policies.

Established a dedicated Out-of-Band Management (OOBM) network for secure administration.

The Exploit (Red Team):

Simulated a legacy Point of Sale (POS) system transmitting transaction data to a backend server over unencrypted HTTP.

Utilized the FortiGate’s built-in Packet Capture (PCAP) engine to sniff the internal wire.

Exported the traffic to Wireshark, successfully intercepting the raw TCP stream and extracting cleartext credit card numbers and CVV data in transit.

The Takeaway:
Firewall policies that simply "allow port 80" are not enough. This lab was a perfect hands-on demonstration of why deep packet inspection and forced TLS/HTTPS encryption are critical for modern application security, especially in financial or retail environments.

(Attach your 3 images here: The GNS3 Topology, the FortiOS Firewall Policy, and the Wireshark TCP Stream showing the stolen data).





