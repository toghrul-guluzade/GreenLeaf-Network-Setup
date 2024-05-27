# Network Setup Project for GreenLeaf Wellness Center


## Course Information
- **Course**: CSCI – 2303 – 20262: Intro to Computer Networks
- **Instructor**: Malak Gasimova
- **Date**: May 8, 2024

## Project Overview
This project aimed to create an imaginary network for the GreenLeaf Wellness Center. The center should consist of two network facilities: one for guests and another for staff, including various types of end-user devices.

To meet the requirements, I selected a Cisco 1941 router for communication with the ISP, serving as the default gateway. Two 2960-24TT switches were set up to establish two sub-networks for the Staff and Guest facilities. DHCP servers were added to each sub-network to provide IP addresses automatically.

## Network Configuration

### Router
- **Hostname**: GreenLeaf
- **Password**: GreenLeaf12345

#### Router Interface Connections
| Router Interface            | Switch Interface   |
|-----------------------------|--------------------|
| Gigabit Ethernet 0/0 (Staff) | Gigabit Ethernet 0/1 |
| Gigabit Ethernet 0/1 (Guest) | Gigabit Ethernet 0/1 |

### Staff Sub-network (Switch)
- **Hostname**: GreenLeaf-Staff
- **Password**: GreenLeaf12345

#### Wireless Access Point
- **SSID**: GreenLeaf-Staff
- **Password**: GreenLeaf2024

#### DHCP Server
- **IPv4 address**: 192.168.10.2

#### End Devices
- Computer for Reception
- Six office computers
- Printer
- Wireless Sound System
- DHCP Server
- Wireless Access Point
  - Tablet
  - Smartphone

#### Staff Switch Interface Connections
| Device Name           | Staff Switch Interface | End Device Port |
|-----------------------|------------------------|-----------------|
| Router                | Gigabit Ethernet 0/1   | Gigabit Ethernet 0/0 |
| DHCP Server           | Fast Ethernet 0/1      | Fast Ethernet 0 |
| Wireless Access Point | Fast Ethernet 0/2      | Port 0          |
| Printer               | Fast Ethernet 0/3      | Fast Ethernet 0 |
| Reception PC (Gogol)  | Fast Ethernet 0/4      | Fast Ethernet 0 |
| PC 1 – PC 6           | Fast Ethernet 0/5 - 0/10 | Fast Ethernet 0 |

#### Devices Connected via Wireless Access Point
- Yoga Studio (Speaker)
- Goncharov’s tablet
- Lermontov’s phone

### Guest Sub-network (Switch)
- **Hostname**: GreenLeaf-Guest
- **Password**: GreenLeaf12345

#### Wireless Access Point
- **SSID**: GreenLeaf-Guest
- **Password**: GreenLeaf2024

#### DHCP Server
- **IPv4 address**: 192.168.20.2

#### End Devices
- DHCP server
- Laptop connected with ethernet cable to switch
- Some other wireless devices

#### Guest Switch Interface Connections
| Device Name           | Guest Switch Interface | End Device Port |
|-----------------------|------------------------|-----------------|
| Router                | Gigabit Ethernet 0/1   | Gigabit Ethernet 0/0 |
| DHCP Server           | Fast Ethernet 0/1      | Fast Ethernet 0 |
| Wireless Access Point | Fast Ethernet 0/2      | Port 0          |
| Tolstoy’s laptop      | Fast Ethernet 0/3      | Fast Ethernet 0 |

#### Devices Connected via Wireless Access Point
- Bulgakov’s smartphone
- Sharik’s laptop
- Dostoyevsky’s laptop
- Pushkin’s smartphone

## Node Configuration
After establishing the network connection, I configured the network using Cisco IOS via the terminal. The router was configured first, assigning IP addresses to each interface individually and activating them with the `no shutdown` command. Settings were saved using the `copy running-config startup-config` command.

Servers were added to the network, and DHCP functionalities were enabled and configured with the corresponding IP addresses. The IP configuration settings for all devices were changed from static to DHCP. A wireless access point was added and configured on port 1 with WPA2-PSK for authentication.

For security, banners and passwords were added to all routers and switches after completing the network setup.

## Testing The Network
After successfully establishing the network at GreenLeaf Wellness Center, it gained popularity among renowned writers who used it frequently. They tested the network connectivity by pinging each other’s devices to ensure seamless communication.

![Ping from Dostoyevsky’s device to Reception (Gogol’s device)](GreenLeaf-Network-Setup/media
/image1.png)

Dostoyevsky tested the connection with Gogol and found it working well. However, Sharik reported issues with his internet connection, which were resolved by verifying the WiFi password.

![Ping and traceroute to Sharik’s default gateway](GreenLeaf-Network-Setup/media
/image2.png
)
![Ping and traceroute to Pushkin’s device](GreenLeaf-Network-Setup/media
/image3.png)

Sharik realized he had not entered the WiFi password correctly.



## Resources
- Bhalodia, C. (n.d.). How to configure DHCP server | DHCP server configuration step by step [Video]. YouTube. Retrieved from [http://www.youtube.com/watch?v=ZCz9rRhzNy4](http://www.youtube.com/watch?v=ZCz9rRhzNy4)
- NetworkChuck. (n.d.). DO NOT design your network like this!! // FREE CCNA // EP 6 [Video]. YouTube. Retrieved from [http://www.youtube.com/watch?v=wwwAXlE4OtU](http://www.youtube.com/watch?v=wwwAXlE4OtU)
- Gurutech Networking Training. (n.d.). CCNA DAY 62: WLAN Configuration - Wireless Access Points Configuration Using Cisco Packet Tracer [Video]. YouTube. Retrieved from [http://www.youtube.com/watch?v=llHpl5Fg9kQ](http://www.youtube.com/watch?v=llHpl5Fg9kQ)
- Cisco. (n.d.). IP Addressing: DHCP Configuration Guide, Cisco IOS Release 15SY. Retrieved from [https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/ipaddr_dhcp/configuration/15-sy/dhcp-15-sy-book/config-dhcp-server.html](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/ipaddr_dhcp/configuration/15-sy/dhcp-15-sy-book/config-dhcp-server.html)
