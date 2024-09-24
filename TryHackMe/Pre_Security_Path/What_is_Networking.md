Answer the questions below

What is the key term for devices that are connected together?
Answer:
```
Network
```
Who invented the World Wide Web?
Answer:
```
Tim Berners-Lee
```

Devices have the same thing: two means of identification, with one being permeable. These are:

- An IP Address
- A Media Access Control (MAC) Address -- think of this as being similar to a serial number.

An **IP** address is a set of numbers that are divided into four octets. The value of each octet will summarise to be the IP address of the device on the network. This number is calculated through a technique known as IP addressing & subnetting, but that is for another day. What's important to understand here is that IP addresses can change from device to device but cannot be active simultaneously more than once within the same network.

**MAC Addresses**
Devices on a network will all have a physical network interface, which is a microchip board found on the device's motherboard. This network interface is assigned a unique address at the factory it was built at, called a **MAC** (**M**edia **A**ccess **C**ontrol ) address. The MAC address is a **twelve-character** hexadecimal number (_a base sixteen numbering system used in computing to represent numbers_) split into two's and separated by a colon. These colons are considered separators. For example, _a4:c3:f0:85:ac:2d_. The first six characters represent the company that made the network interface, and the last six is a unique number.

**Practical**  
The interactive labs simulate a hotel Wi-Fi network where you have to pay for the service. You'll note that the router is not allowing Bob's packets ( blue) to the TryHackMe website and is placing them in the bin, but Alice's packets (green) are going through fine because she has paid for Wi-Fi. Try changing Bob's MAC address to the same as Alice's to see what happens.  

Deploy the interactive lab and proceed to answer the following questions below.

Let's just sort out all the easy questions first:

What does the term "IP" stand for?
```
Internet Protocol
```
What is each section of an IP address called?
```
Octet
```
How many sections (in digits) does an IP address have?
```
4
```
What does the term "MAC" stand for?
```
Media Access Control
```
Deploy the interactive lab using the "View Site" button and spoof your MAC address to access the site.  What is the flag?
![[11.png]]