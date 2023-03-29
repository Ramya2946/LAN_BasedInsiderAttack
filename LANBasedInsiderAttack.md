# LANBasedInsiderAttack.md
# ETTERCAP


### Ettercap supports active and passive dissection of many protocols (even encrypted ones) and includes many feature for network and host analysis. Data injection in an established connection and filtering (substitute or drop a packet) on the fly is also possible, keeping the connection synchronized. Many sniffing modes are implemented, for a powerful and complete sniffing suite. It is possible to sniff in four modes: IP Based, MAC Based, ARP Based (full-duplex) and PublicARP Based (half-duplex). Ettercap also has the ability to detect a switched LAN, and to use OS fingerprints (active or passive) to find the geometry of the LAN. This package contains the Common support files, configuration files, plugins, and documentation. You must also install either ettercap-graphical or ettercap-text-only for the actual GUI-enabled or text-only ettercap executable, respectively.

# ARP Poisoning
### ARP Poisoning (also known as ARP Spoofing) is a type of cyber attack carried out over a Local Area Network (LAN) that involves sending malicious ARP packets to a default gateway on a LAN in order to change the pairings in its IP to MAC address table. ARP Protocol translates IP addresses into MAC addresses. 


# Performing Password stealing (over plaintext) using ARP Cache Poisoning attacks
- We first scan for host ip address

![Screenshot (315)](https://user-images.githubusercontent.com/123251017/227991197-e922c1d8-5063-494c-888a-035b9276a975.png)


- We get the list of scanned Host list in the Ettercap as shown in the image , here we can find our host ip address

![Screenshot (316)](https://user-images.githubusercontent.com/123251017/227992069-07281334-6560-4d1d-9ec2-75ed34fc4da7.png)

- Select host ip address and add it to the target.
- Choose ARP poisoning from MITM
- Now open a web page in the victims machine and enter the login credentials.

![Screenshot (318)](https://user-images.githubusercontent.com/123251017/227992948-c496d7db-8f29-4fa4-a2ab-92254b552b02.png)

- Whenictim enters the login credentials, we can see the USER & PASS are captured.

![Screenshot (319)](https://user-images.githubusercontent.com/123251017/227993599-21b69ce9-1cf6-4f9b-9be1-5ba2b9bc73f2.png)


# Perform Denial of Service (DoS) attacks using ARP Cache Poisoning attacks 

### DOS ATTACK:
- In computing, a denial-of-service attack is a cyber-attack in which the perpetrator seeks to make a machine or network resource unavailable to its intended users by temporarily or indefinitely disrupting services of a host connected to a network.

### The following steps are to be followed to perform this attack
1. Open ettercap , scan hosts and add the victim's IP address to the target.
2. Start ARP Poisoning and select DOS attack plugin and enter victim's IP address and fake host IP address
3. To check the website is accessable or not we will open any site in the victim's machine.
4. Then we can see that the page does'nt respond .

![Screenshot (320)](https://user-images.githubusercontent.com/123251017/227993985-1c68b259-cdc8-4678-b1b2-c01834620e34.png)

#  Perform DNS Spoofing attack using ARP Cache Poisoning attacks 

- Make the ec_uid and ec_guid values as zero ,give some domain name and assign the attackers IP address.

![image](https://user-images.githubusercontent.com/68326118/227768095-16ce5d30-d4d8-42fc-a58e-01e464aa4a53.png)

![image](https://user-images.githubusercontent.com/68326118/227767987-e11b0d5b-f7db-4aa4-9880-4478eb4f5843.png)

![image](https://user-images.githubusercontent.com/68326118/227768060-efe57151-bf1e-4b9c-a06c-c5cc0578e629.png)

-  start apache2 and then open the ettercap 
- scan for the hosts and add the attackers host to the target.
- Choose ARP Spoofing and then DNS spoofing plugin
- When we open snapchat.com in the attacker's machine web browser , we can see the spoofed web page.

![image](https://user-images.githubusercontent.com/68326118/227766876-3e0a3252-2be0-4a24-897d-6d7221a833a1.png)

![Screenshot (325)](https://user-images.githubusercontent.com/123251017/227994799-4596da6d-83ac-4d48-b34d-2d7c78d8fd3d.png)

#  Invoke ‘sslstrip tool’ for stealing passwords from any machine that is connected to a LAN by stripping the HTTPS connection. 

 1)Open ettercap tool and scan the host 
 2)select the vicitm's ip address and add to target 1 
 3)Start MITM Attacks of ARP Poisoning 
 4)And select the SSL Strip plugin 
 
![image](https://user-images.githubusercontent.com/68326118/227952722-2608aaac-f09f-428e-bafc-312c185c2427.png)

-  ssl striping on the victim's machine 
![Screenshot (327)](https://user-images.githubusercontent.com/123251017/227995721-7881456b-462d-4a6f-bafb-2064a0a60843.png)

# arp_cop and scan_poisoner plugins to learn about the detection of ARP attacks
### arp_cop: It reports suspicious ARP activity by passively monitoring ARP requests and replies. It can report ARP posioning attempts, or simple IP-conflicts or IP-changes. We follow following steps to perform the attack
- Open ettercap and select arp_cop plugin.
- Open ettercap in another machine and scan the hosts.
- Add the first machine's IP address as Target.

![image](https://user-images.githubusercontent.com/68326118/228004106-ac3f82de-af6f-4dc2-8667-dc6995d64b32.png)

- Start the ARP poisoning in second machine.
- We can see in first machine's window that it reports the ARP activity.

![image](https://user-images.githubusercontent.com/68326118/228004219-3596fcc9-60ff-4ae8-b779-bbf527e378ef.png)

### scan_poisoner scans if someone is poisoning between the user machine and the hosts in the scanned list. It checks whether if two hosts in the list have same MAC address.
1)Open ettercap and select the scan_poisoner plugin.
2)Open ettercap in another machine and scan the hosts.
3)Add the first machine's IP address as Target.
4)Start the ARP Poisoning.
5) We can see that one host is replying to other in the lists of hosts that captured by scan_poisoner.


- if there is no host poisoning other host the output will be like below

![image](https://user-images.githubusercontent.com/68326118/228006787-18b8b82c-f1b5-4bdd-a3ab-edb92dfe90e3.png)

- if there is host poisoning other host the output will be like below 
- 
![image](https://user-images.githubusercontent.com/68326118/228007089-6a2ad6b4-0021-4c28-80ff-0e88a57d0d49.png)
