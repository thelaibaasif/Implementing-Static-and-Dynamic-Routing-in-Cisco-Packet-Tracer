# Implementing Static and Dynamic Routing in Cisco Packet Tracer -Computer Networks 


## Description
This project involves setting up a network with three subnets (Network A, B, and C) using Cisco Packet Tracer. Network A and Network B are connected via static routing, while Network A and Network B are connected to Network C using a dynamic routing protocol. The aim is to ensure full connectivity between all PCs in the network.

## Table of Contents
- [Introduction](#introduction)
- [Network Topology](#network-topology)
- [Requirements](#requirements)
- [Configuration Steps](#configuration-steps)
  - [Static Routing](#static-routing)
  - [Dynamic Routing](#dynamic-routing)
- [Verification](#verification)
- [Conclusion](#conclusion)
- [License](#license)

## Introduction
In this project, we will configure both static and dynamic routing in a network to ensure that all PCs can communicate with each other. Static routing will be used between Network A and Network B, while a dynamic routing protocol will be employed between Network A, B, and C.

## Network Topology
Below is the network topology used for this project:


## Requirements
- Cisco Packet Tracer installed on your computer
- Basic understanding of networking concepts
- Basic knowledge of Cisco IOS commands

## Configuration Steps

### Static Routing
1. Configure IP addresses on all interfaces of the routers.
2. Set up static routing between Network A and Network B.

**Router1 Configuration:**
```sh
Router1(config)# interface fa0/0
Router1(config-if)# ip address 192.168.1.1 255.255.255.0
Router1(config-if)# no shutdown

Router1(config)# interface s0/0/0
Router1(config-if)# ip address 192.168.2.1 255.255.255.0
Router1(config-if)# no shutdown

Router1(config)# ip route 192.168.3.0 255.255.255.0 192.168.2.2

**Router2 Configuration:**
```sh
Router2(config)# interface fa0/0
Router2(config-if)# ip address 192.168.3.1 255.255.255.0
Router2(config-if)# no shutdown

Router2(config)# interface s0/0/0
Router2(config-if)# ip address 192.168.2.2 255.255.255.0
Router2(config-if)# no shutdown

Router2(config)# ip route 192.168.1.0 255.255.255.0 192.168.2.1

**Dynamic Routing**
```sh
Enable a dynamic routing protocol (e.g., OSPF) on Router1, Router2, and Router3.
Configure the dynamic routing protocol to include the networks of Router1, Router2, and Router3.
Router1 Configuration:

**Router1(config)# router ospf 1**
Router1(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router1(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router2 Configuration:

**Router2(config)# router ospf 1**
Router2(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router2(config-router)# network 192.168.3.0 0.0.0.255 area 0
Router3 Configuration:

**Router3(config)# interface fa0/0**
Router3(config-if)# ip address 192.168.4.1 255.255.255.0
Router3(config-if)# no shutdown

**Router3(config)# router ospf 1**
Router3(config-router)# network 192.168.3.0 0.0.0.255 area 0
Router3(config-router)# network 192.168.4.0 0.0.0.255 area 0

**Verification**
Use the ping command on each PC to ensure they can communicate with each other.
Verify the routing tables on each router using the show ip route command to ensure correct route propagation.
Example:

Router1# show ip route
Router2# show ip route
Router3# show ip route

**Conclusion**
```sh
By following the above steps, you should have successfully configured static and dynamic routing in Cisco Packet Tracer, ensuring that all PCs can communicate with each other across different networks.

**License**
```sh
This project is licensed under the MIT License - see the LICENSE file for details.

**Additional Resources**
```sh
Cisco Packet Tracer Installation Guide
Cisco IOS Command Reference

### Additional Files to Include in the GitHub Repository
1. **Network Topology Diagram**: A visual representation of the network topology used in the examples.
2. **Packet Tracer File**: The `.pkt` file containing the network setup in Cisco Packet Tracer.
3. **Configuration Files**: Text files containing the configuration commands for each router.
4. **LICENSE**: A file detailing the license under which the project is distributed (e.g., MIT License).
5. **CONTRIBUTING.md**: Guidelines for contributing to the project.
6. **.gitignore**: A file specifying which files and directories to ignore in the repository.





