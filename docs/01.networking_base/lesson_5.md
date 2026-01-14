# 📘 ARP – Address Resolution Protocol (Simple Guide)

### 🧠 What is ARP?

- ARP (Address Resolution Protocol) is a rule that helps a computer find the MAC address when it already knows the IP address.

#### 📌 In simple words:

- ARP connects IP Address ➜ MAC Address

#### 🤔 Why Do We Need ARP?

- Computers talk using MAC addresses inside a LAN
- But humans and networks use IP addresses
- ARP helps match IP → MAC so data reaches the correct device

#### 🔄 How ARP Works (Behind the Scene)

- Computer A wants to send data to Computer B
- Computer A knows B’s IP address, but not the MAC
- Computer A sends an ARP Request to everyone:
  “Who has this IP address?”
- Computer B replies with its MAC address
- Computer A saves this MAC in its ARP Table
- Data is sent successfully 🎉
  ![alt text](images/How-Does-ARP-Work.png)

#### 📋 What is an ARP Table?

#### An ARP Table is a small list stored in the computer’s memory.

#### It contains:

- IP Address
- MAC Address

#### 📌 This table helps the computer remember devices so it does not ask again and again.

#### 💾 How MAC Addresses Are Stored in ARP Table

#### When ARP gets a reply:

- The IP and MAC pair is saved in the ARP table
- It is stored temporarily (not permanent)
- Entries are removed after some time if not used

#### Example ARP Table Entry:

192.168.1.1 → 00:1A:2B:3C:4D:5E

#### 🎯 Purpose of ARP

- Finds MAC address using IP address
- Helps devices communicate inside LAN
- Reduces network delay
- Makes data delivery faster and accurate

#### 🧑‍💻 Commands to Check ARP Table

#### ✅ Windows

> arp -a

#### ✅ Linux / macOS

> arp

#### 🧾 Sample ARP Table Output

![alt text](images/ARP_TABLE_OUTPUT.PNG)

- Internet Address → IP Address
- Physical Address → MAC Address

---

#### ⚠️ Important Points

- ARP works only inside Local Area Network (LAN)
- ARP uses broadcast messages
- ARP table entries are dynamic (temporary)

---

### 📘 Quick Summary

- ARP means Address Resolution Protocol
- It matches IP address to MAC address
- MAC addresses are saved in ARP table
- ARP table helps faster communication
- Checked using arp -a
- 🎉 ARP makes networking work smoothly!

---
