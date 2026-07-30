# Try Hack Me Networking Room(Included additional details for clarity)

> **URL:** https://tryhackme.com/module/networking

---

## Networking Concepts

### Task 1:Read the introduction.

### Task 2:The OSI (Open Systems Interconnection) model

- The OSI model was developed by ISO(International Organization for Standardization)
- It is a conceptual model which explains how computer networks work.
- It has 7 layers :

      1.Physical Layer

      2.Data Link Layer

      3.Networking Layer

      4.Transport Layer

      5.Session Layer

      6.Presentation Layer

      7.Application Layer 
- The physical layer is layer 1 while the application layer is layer 7.
- data travels from layer1(physical) to layer7(application) when receiving and from layer7(application) to layer1(physical) when sending.
#### Layer 1-Physical Layer
- concerned with the physical connection between devices(like the topology).
- The type of wires used and representing data as binary bits.
- Attacks that could be carried out on this layer include ones that have physical nature like cutting the wires,eavesdropping,etc..

#### Layer 2-DataLink Layer
- Is concerned with transfer(switching) of data(frames) between nodes.
- The addressing mechanism of this layer is called mac address or the physical address.
-Attacks that could be carried out on this layer include: Mac spoofing,ARP spoofing,VLAN hopping,etc...

#### Layer 3-Network Layer
- Unlike the datalink layer,the network layer is responsible for connecting separate networks.
- concerned with routing packets between nodes.
- The addressing mechanism of this layer is called an ip-address. 
- Types of IP addresses can be classified as: directed broadcast,local broadcast,loop back(127.0.0.1),Private,Public,auto configured,reserved.
-  Attacks that could be carried out on this layer include:IP spoofing,DDOS and DOS attacks,routing protocol attacks.

#### Layer 4-Transport Layer
- The transport layer is concerned with the end-to-end communication between running applications before a session is established.
- Layer 4 protocols include TCP(transmission controll protocol) which is also called a connection oriented protocol and uses three way handshake: SYN,SYN-ACK,ACK and UDP(user datagram protocol) which is a connectionless protocol.
- The layer 4 uses port numbers as an addressing mechanism.
- port numbers are numbers which are assigned to application or services running on a machine. e.g-HTTP:80,mysql:3306,telnet:23,smtp:587,pop3:110...
- ip address + port number is called socket address.e.g-`192.456.4.2:80`
- Attacks that could be carried out on this layer include:Man In The Middle attacks,Port scanning using the popular network mapping tool nmap or other tools,buffer overflow,etc...

#### Layer 5-Session Layer
- This layer is responsible for establishing,maintaining and terminating a session after authentication.
- Attacks that could be carried out on this layer include:session hijacking,brute force attacks,etc...

#### Layer 6-Presentation Layer
- This layer is concerned with things like encoding,compression and encryption of data.
-  Attacks that could be carried out on this layer include:encryption attacks,compression attacks,etc...

#### Layer 7-Application Layer
- This is a layer which most people are familiar with.
- This layer provides services and protocols like HTTP(hyper text transfer protocol),FTP(file transfer protocol),DNS(domain name system),email services like(pop3,smtp,imap).
- Attacks that could be carried out on this layer include attacks exploiting flaw in a application:SQL injection,XSS,SSRF,broken authentication,etc...

### Task 3:The TCP/IP model
- The TCP/IP model(Transmission Control Protocol/Internet Protocol) model is regarded as an implemented model unlike the OSI model which is conceptual.
- It has 5 layers:

       1.Application Layer(contains the OSI model session,presentation and application layers)

       2.Transport Layer

       3.Network Layer

       4.Datalink Layer

       5.Physical Layer

### Task 4:IP addresses and subnets
- An ip address is a layer 3(Networking layer) addressing mechanism which is used for uniquely identifying devices(hosts) that are connected to a network.
- There are 2 widely known types of ip addresses.The IPV4 and IPV6.The IPV4 is a 32 bit addressig which is capable of producing 2^32 addreses.Because the number of available IPV4 addresses are not enough,the IPV6 was introduced which is a 128 bit system capable of handling 2^128 addresses.
- The IPV4 is devided in to 4 segments(octets).each octet is capable of representing numbers from 0-255(from 00000000.00000000.00000000.00000000 to 11111111.11111111.11111111.11111111 in binary.)
- There are 5 classes of IP addresses:A(0.0.0.0-126.255.255.255),B(128.0.0.0-191.255.255.255),C(192.0.0.0-223.255.255.255),D(224.0.0.0-239.255.255.255) and E(240.0.0.0-255.255.255.255).
- To view the private ip addresses on linux/unix based devices,type `ifconfig` in to the terminal.For windows,`ipconfig` 
- To see the public ip-address on a linux machine,use `curl ifconfig.me`
- Subnetting refers to dividing a single physical network in to several logical units by borrowing bits from the host bits and adding it to the network bits.

 ### Task 5:UDP and TCP
- The UDP(User Datagram Protocol) and the TCP(Transmission Control Protocols) are transmission layer protocols.
- The UDP is a connection less protocol which means it doesn’t establish a connection and it’ll transmit regardless.
- The UDP is faster but less reliable used for things like streaming.
- The TCP is also called a connection oriented protocol. It insures reliable data delivery despite being relatively slower compared to UDP.
- It uses what is called a three way handshake to establish a connection.

       1.SYN:a synchronization packet is sent form a device to a server.

       2.SYN-ACK:the server responds with s SYN-ACK packet.

       3.ACK:The handshake is completed and the device sends an acknowledgement to the server.

### Task 6:Encapsulation
- Encapsulation means to add layers(might be a header or a trailer) on a data received then passing it downwards to the next layer.
- This includes four steps on four separate layers.

       1.Application:When the user send a data for example an email,it is formatted according to the protocols used and then sent down to the next layer.

       2.Transport:on this layer,using either TCP or UDP,a segment(TCP) or a datagram(UDP) is formed.

       3.Network packet:at the networking layer,a packet is formed by adding an IP header.

### Task 7:Telnet
- Telnet is a protocol which allows the control of a system via the CLI by running commands remotely.
- It runs on port 23 by default.
- To connect via telnet we use the command `$telnet MACHINE_IP port`.
- example `$telnet 10.130.143.48 80`

### Task 8:Read the Conclusion