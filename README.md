<img width="506" height="528" alt="asa fireeewall" src="https://github.com/user-attachments/assets/7274fe32-e466-41e6-8a06-d3c987ddf6cf" />
1. Zone-Based Security Interfaces
Configured physical firewall interfaces to separate network segments based on trust levels.
* Outside Zone: GigabitEthernet1/1` connected to the public ISP with a security level of `0`.
* Inside Zone: `GigabitEthernet1/2` connected to the internal LAN with a security level of `100`.
* DMZ Zone: `GigabitEthernet1/3` configured for a LAN failover link with a security level of `50`.

 L<img width="649" height="401" alt="firewallasa" src="https://github.com/user-attachments/assets/261d8195-776d-4b0a-978f-d2f1a54a5283" />
<img width="354" height="340" alt="fireeeewall asa" src="https://github.com/user-attachments/assets/a8ba8ac5-44dc-4301-ac96-42bc203a68a4" />
<img width="699" height="289" alt="fir" src="https://github.com/user-attachments/assets/9a5ea499-2a07-4f47-8d16-4cf2fe238925" />
<img width="401" height="513" alt="ASA Firwall" src="https://github.com/user-attachments/assets/996de508-688f-4388-9501-00e3cf6e2c81" />
ists (ACLs), Firewalling, DHCP Server Management
2. Dynamic NAT (Network Address Translation) Policies
Designed and deployed Auto-NAT policies to allow internal VLAN users safe access to the Internet. Created network objects to translate traffic dynamically to the public outside interface for:
* Management and main subnets (`INSIDE-NET`)
* Production and departmental networks (`OBJ_VLAN_10` through `OBJ_VLAN_40`)
3. Access Control Lists & Modular Policy Framework (MPF)
* Traffic Filtering: Created an extended Access Control List (`INSIDE`) to explicitly permit ICMP (ping) traffic and bound it to the inside interface.
* Deep Packet Inspection: Configured a global service policy to inspect application traffic layer services including DNS, FTP, ICMP, and TFTP.
4. Enterprise Routing Engine
Built a routing topology by writing static routing paths across the security engine.
* Configured a Gateway of Last Resort** pointing default traffic (`0.0.0.0/0`) out to the upstream provider gateway (`203.0.113.1`).
* Established static routes to internal gateway `192.168.1.2` to safely forward incoming data down to core internal subnets.
Hardware & Platforms Used
* Appliance: Cisco ASA 5500 Series / Adaptive Security Appliance
* Operating System:** Cisco ASA Software
* Management Tools: Command Line Interface (Cisco IOS-like CLI)
