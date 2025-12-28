


## 2.7 REMOTE ACCESS  USING TELNET CONFIGURATION 
### 1. Assign IP address to the router and host device 

<br> en
<br> conf t
<br> hostname R1

<br> interface gigabitEthernet 0/0/0
<br> ip address 192.168.1.1 255.255.255.0
<br> no shutdown 
<br> exit

<br> interface gigabitEthernet 0/0/1
<br> ip address 192.168.2.1 255.255.255.0
<br> no shutdown 
<br> exit 

### 2. Configure the management IP address and default gateway on the switch 
<br> int vlan 1
<br> ip address 192.168.2.254 255.255.255.0
<br> no shut
<br> exit
<br> ip default-gateway 192.168.2.1 


### 3. Configure hostname, domain name, enable password, username, and password 
<br> hostname S1
<br> ip domain name cisco.com 
<br> username Admin password cisco
<br> enable password cisco 

### 4. Configure the local login and transport input telnet on vty interface 

<br> line vty 0 15 
<br> login local 
<br> transport input telnet 

### 5. On the Admin-PC, ping the management IP address 
<br> ping 192.168.2.254

### 6. On the Admin-PC, telnet to the switch using the command 
<br> telnet 192.168.2.254

