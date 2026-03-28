# Cisco-Packet-Tracer-Labs
A collection of networking labs focusing on CCNA/Network+ concepts including VLANs, Routing, and Security

🌐 Lab: VLAN Logical Segmentation & Layer 2 Security
📌 Project Overview

This lab demonstrates the implementation of Virtual Local Area Networks (VLANs) on a Cisco 2960 Switch using Cisco Packet Tracer. The goal was to take a flat network and segment it into three distinct departments (IT, HR, and Finance) to improve security and reduce broadcast traffic.

🎯 Objective

Design a network where three departments share a single physical switch but remain logically isolated.

Configure access ports and assign them to specific VLAN IDs.

Verify that devices on the same subnet but different VLANs cannot communicate (Layer 2 Isolation).

🛠️ Technical Setup

Software: Cisco Packet Tracer

Hardware: 1x Cisco Catalyst 2960 Switch

End Devices: 3x Generic PCs

Addressing: All devices reside on the 192.168.1.0/24 subnet.

Department	VLAN ID	Port Assignment	IP Address
IT	10	Fa0/1	192.168.1.10
HR	20	Fa0/2	192.168.1.11
Finance	30	Fa0/3	192.168.1.12
💻 Configuration (Cisco IOS)

The following commands were used to initialize the VLAN database and assign physical interfaces:

Bash
# Creating the VLANs
Switch(config)# vlan 10
Switch(config-vlan)# name IT
Switch(config)# vlan 20
Switch(config-vlan)# name HR
Switch(config)# vlan 30
Switch(config-vlan)# name FINANCE

# Assigning interfaces to Access Mode
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
🔍 Verification & Testing

VLAN Database Check: Ran show vlan brief to confirm ports were correctly mapped to their respective IDs.

Connectivity Test: Attempted a ping from the IT PC to the HR PC.

Expected Result: Request Timed Out.

Actual Result: Request Timed Out.

Conclusion: The switch successfully dropped the frames because they belonged to different broadcast domains, confirming the security of the logical segmentation.

🧠 Skills Demonstrated

Cisco IOS Command Line Interface (CLI)

Layer 2 Switching & Segmentation

Broadcast Domain Management

Network Troubleshooting & ICMP Testing
