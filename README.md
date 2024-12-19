# Network Design and Implementation Considerations

## General Design Considerations
- **Three routers per floor**:
  - All placed in the server room in the IT department.
  - Connected to each other using fiber optic cables.
- **Layer-2 Switches**:
  - Each floor will have one or more Layer-2 switches placed on the respective floor.
  - Switches will connect to routers using Gigabit Ethernet ports.
- **Wi-Fi Network**:
  - Each floor will have a Wi-Fi network (Access Point) to connect laptops and phones.
- **Printers**:
  - Each department will have a dedicated printer.

---

## Network Addressing
- **Private IP Address**: `172.16.0.0/16`
- **Subnetting and VLSM**: Utilize for IPv4 addressing to optimize IP usage.
- **IPv6 Addressing**:
  - Use network address `2001:ABCD:1234:A::/64` for devices in the IT department.
  - Assign IPv6 addresses manually.

---

## VLAN Configuration

### 1st Floor
- **Reception**: VLAN-10, Number of Hosts: 200.
- **Store**: VLAN-11, Number of Hosts: 120.
- **Logistics**: VLAN-12, Number of Hosts: 60.

### 2nd Floor
- **Finance**: VLAN-20, Number of Hosts: 50.
- **HR**: VLAN-21, Number of Hosts: 50.
- **Sales**: VLAN-22, Number of Hosts: 50.

### 3rd Floor
- **Admin**: VLAN-30, Number of Hosts: 10.
- **IT**: VLAN-31, Number of Hosts: 10.

---

## Routing and Connectivity
- **Routing Protocol**: OSPF for dynamic route advertisement.
- **Static Routes**: Configure as a backup for OSPF.
- **DHCP**:
  - Configure on all routers.
  - Devices (except servers and routers) should obtain IP addresses automatically.
- **Reachability**:
  - Ensure all devices on the network/VLAN are reachable from any other network/VLAN.

---

## Device Configuration
- **Hostnames**: Assign a unique hostname to all switches and routers.
- **Interface Names**: Assign meaningful interface names for all devices connected to switches and routers.
- **Remote Access**:
  - Configure **SSH** on all switches and routers.
- **Testing**:
  - Add two PCs in the IT department to test remote access to any location or department.

---

## IT Department Setup
- **Server**: 
  - Host the following services:
    - **Web Server**: Serve the company website (`www.qtire.com`).
    - **FTP Service**: Save important company files.
    - **TFTP Service**: Store configuration files for switches and routers.
    - **Mail Server**: Provide email services.
  - Create a simple HTML page for the company and host it on the web server.
- **PCs**:
  - Assign both IPv4 and IPv6 addresses for testing.
- **IPv6**:
  - Use manual IPv6 addressing for the IT department using `2001:ABCD:1234:A::/64`.

---


