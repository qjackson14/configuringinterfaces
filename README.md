<p align="center">

</p>


<h2>Video Demonstration</h2>

- ### [YouTube: Day 9 Configuring Interfaces](https://www.youtube.com/watch?v=7NGYdTWudxY)

<h2>Environments and Technologies Used</h2>

- Jeremy's IT Lab Youtube Channel
- Cisco Packet Tracer
  

  
<h2>Operating Systems Used </h2>

- Cisco IOS


<h2>Step-by-Step</h2>

<b>🟢 Part 1 — Configure R1</b>

<b> 🔹 Set Hostname</b>

- Access R1 CLI.

- Enter privileged mode: enable

- Enter global configuration mode: configure terminal

- Set hostname: hostname R1

  <b>🔹 Configure G0/0 Interface</b>

- Enter interface configuration mode: interface g0/0

- Verify interface status: do show ip interface brief

- Assign IP address: ip address 172.16.255.254 255.255.0.0

- Set speed: speed 1000

- Set duplex: duplex full

- Add description: description ## to SW1 ##

- Enable interface: no shutdown

- Verify status again: do show ip interface brief

  <b>🔹 Configure Unused Interfaces</b>

- Enter interface range mode: interface range g0/1 - 2

- Add description: description ## not in use ##

  <b>🔹 Verify and Save</b>

- Verify configuration: do show running-config

- Exit configuration mode: end

- Save configuration: copy running-config startup-config

- Verify saved configuration: show startup-config

<b>🟢 Part 2 — Configure PCs</b>
<b>🔹 PC1</b>

- Click PC1 → Config → FastEthernet0

- Set IP address: 172.16.0.1

- Confirm subnet mask auto-fills to 255.255.0.0

- Confirm default gateway is 172.16.255.254

  <b>🔹 PC2</b>

- Click PC2 → Config → FastEthernet0

- Set IP address: 172.16.0.2

- Confirm subnet mask auto-fills to 255.255.0.0

<b>🔹 PC3</b>

- Click PC3 → Config → FastEthernet0

- Set IP address: 172.16.0.3

- Confirm subnet mask auto-fills to 255.255.0.0

<b>🔹 PC4</b>

- Click PC4 → Config → FastEthernet0

- Set IP address: 172.16.0.4

- Confirm subnet mask auto-fills to 255.255.0.0

<b>🟢 Part 3 — Configure SW1</b>
<b>🔹 Set Hostname</b>

- Access SW1 CLI

- Enter privileged mode: enable

- Enter global configuration mode: conf t

- Set hostname: hostname SW1

<b>🔹 Verify Interfaces</b>

- Check interface status: do show interfaces status

<b>🔹 Configure G0/1 (Connected to R1)</b>

- Enter interface mode: interface g0/1

- Set speed: speed 1000

- Set duplex: duplex full

- Add description: description ## to R1 ##

<b>🔹 Configure G0/2 (Connected to SW2)</b>

- Enter interface mode: interface g0/2

- Set speed: speed 1000

- Set duplex: duplex full

- Add description: description ## to SW2 ##

-🔹 Configure End-Host Ports

- Enter interface range: interface range f0/1 - 2

- Add description: description ## to end hosts ##

-🔹 Disable Unused Ports

- Enter interface range: interface range f0/3 - 24

- Add description: description ## not in use ##

- Disable interfaces: shutdown

-🔹 Verify and Save

- Verify interfaces: do show interfaces status

- Exit configuration mode: end

- Save configuration: write memory

- Verify saved configuration: show startup-config

<b>🟢 Part 4 — Configure SW2</b>
-🔹 Set Hostname

- Access SW2 CLI

- Enter privileged mode: enable

- Enter global configuration mode: conf t

- Set hostname: hostname SW2

-🔹 Verify Interfaces

- Check interface status: do show interfaces status

-🔹 Configure G0/1 (Connected to SW1)
  
- Enter interface mode: interface g0/1

- Set speed: speed 1000

- Set duplex: duplex full

- Add description: description ## to SW1 ##

-🔹 Configure End-Host Ports

- Enter interface range: interface range f0/1 - 2

- Add description: description ## to end hosts ##

-🔹 Disable Unused Ports

- Enter interface range: interface range g0/2, f0/3 - 24

- Add description: description ## not in use ##

- Disable interfaces: shutdown

-🔹 Verify and Save

- Verify interfaces: do show interfaces status

- Exit configuration mode: end

- Save configuration: write

- Verify saved configuration: show startup-config
