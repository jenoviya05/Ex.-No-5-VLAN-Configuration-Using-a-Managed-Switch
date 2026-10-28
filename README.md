## Ex. No: 5  VLAN Configuration Using a Managed Switch
## Date: 28.10.26
________________________________________
# Objective
To configure Virtual Local Area Networks (VLANs) on a managed switch and verify that hosts within the same VLAN can communicate while others cannot.
________________________________________
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Managed Switch (e.g., 2960)<br>
•	4 PCs<br>
•	Straight-through Ethernet cables<br>
________________________________________
# Network Topology Diagram
Description:<br>
•	PC0 and PC1 are assigned to VLAN 10.<br>
•	PC2 and PC3 are assigned to VLAN 20.<br>
•	All PCs are connected to different ports on the same switch.<br>
(Insert screenshot of your Packet Tracer setup here)<br>

<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 27 14 PM" src="https://github.com/user-attachments/assets/a5d39851-59b2-4b3a-ae8e-377e985506bd" />

________________________________________
# IP Addressing Table
Device	VLAN	IP Address	Subnet Mask	Port<br>
PC0	10	192.168.10.1	255.255.255.0	FastEthernet0/1<br>
PC1	10	192.168.10.2	255.255.255.0	FastEthernet0/2<br>
PC2	20	192.168.20.1	255.255.255.0	FastEthernet0/3<br>
PC3	20	192.168.20.2	255.255.255.0	FastEthernet0/4<br>
________________________________________
# Procedure
1.	Open Cisco Packet Tracer and add 4 PCs and 1 Switch.<br>
2.	Connect PC0–PC3 to switch ports FastEthernet0/1 to FastEthernet0/4 respectively.<br>
3.	Assign static IP addresses to each PC as per the IP table.<br>
4.	Enter the Switch CLI and create two VLANs:<br>
o	VLAN 10 for PC0 and PC1<br>
o	VLAN 20 for PC2 and PC3<br>
5.	Assign the respective switch ports to their VLANs.<br>
6.	Use the ping command from PC0 to PC1 (should succeed).<br>
7.	Try pinging from PC0 to PC2 (should fail — different VLANs).<br>
________________________________________
# Commands Used (Switch CLI)
bash<br>
CopyEdit<br>
Switch> enable<br>
Switch# configure terminal<br>

Switch(config)# vlan 10<br>
Switch(config-vlan)# name STAFF<br>
Switch(config-vlan)# exit<br>

Switch(config)# vlan 20<br>
Switch(config-vlan)# name STUDENTS<br>
Switch(config-vlan)# exit<br>

Switch(config)# interface range fastethernet0/1 - 2<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 10<br>
Switch(config-if-range)# exit<br>

Switch(config)# interface range fastethernet0/3 - 4<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 20<br>
Switch(config-if-range)# exit<br>
________________________________________
# Output (Screenshots)
•	VLAN configuration on switch<br>
•	PC IP settings<br>
•	Successful ping between PCs in the same VLAN<br>
•	Failed ping between PCs in different VLANs<br>

## CONFIGURATION 

<img width="1600" height="997" alt="WhatsApp Image 2026-10-28 at 12 27 15 PM" src="https://github.com/user-attachments/assets/f402d871-7df4-4d31-b3d9-e8aefe420a57" />

<img width="1600" height="995" alt="WhatsApp Image 2026-10-28 at 12 27 16 PM (1)" src="https://github.com/user-attachments/assets/3aad1d37-c62e-4d7f-b6b7-cbeb09ec508a" />

<img width="1600" height="997" alt="WhatsApp Image 2026-10-28 at 12 27 16 PM (2)" src="https://github.com/user-attachments/assets/d5647eec-f233-4143-95ce-b00fe3608d42" />

<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 27 16 PM" src="https://github.com/user-attachments/assets/038abd80-a625-4b32-861b-bb84b49c8b56" />

<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 27 17 PM (1)" src="https://github.com/user-attachments/assets/16128909-7f56-4acd-bfad-06a275c56cbf" />

<img width="1600" height="994" alt="WhatsApp Image 2026-10-28 at 12 27 17 PM" src="https://github.com/user-attachments/assets/78c18aa6-2fd6-4b81-8b07-b7b74ec388ac" />


## PING RESULTS

<img width="1600" height="995" alt="WhatsApp Image 2026-10-28 at 12 27 17 PM (5)" src="https://github.com/user-attachments/assets/5952aedd-1ed9-46a5-a69e-6ad60cae42b8" />

<img width="1600" height="997" alt="WhatsApp Image 2026-10-28 at 12 27 17 PM (4)" src="https://github.com/user-attachments/assets/8c568267-e662-4469-b799-857cfae75eef" />

<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 27 17 PM (3)" src="https://github.com/user-attachments/assets/9a4f2510-dc04-404c-b3bc-045f749a695a" />



## SWITCH CONFIG 

<img width="1600" height="999" alt="WhatsApp Image 2026-10-28 at 12 27 17 PM (2)" src="https://github.com/user-attachments/assets/cecd9893-0a26-41f4-84d3-6e1ba40548df" />



________________________________________
# Result
Successfully created and configured VLANs on a managed switch. Verified that only PCs within the same VLAN could communicate with each other.

