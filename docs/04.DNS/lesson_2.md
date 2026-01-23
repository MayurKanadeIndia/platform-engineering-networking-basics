# DNS Master Server Setup (Configuration Settings)

#### Step-1 : Set Hostname, Disable firewalld and NetworkManager.

![alt text](images/master-setup-step1.PNG)

#### Step-2 : Change SELinux Policy From Enforcing to Disabled

![alt text](images/selinux-enforce-disbled.PNG)

---

#### Note: When you configure the VM machine on VMWare then it must be configured with NAT settings to access the Internet on the VM machine.

---

#### Step-3: Location and Initial Settings of "ifcfg-ens33" file.

![alt text](images/asssign_dhcp_for_internet.PNG)

- then, initial settings of "/etc/hosts/" file
  ![alt text](images/system-reboot.PNG)

#### Step-4: Firewall settings from which we will Flush all the rules.

![alt text](images/firewall-setting.PNG)

- to flush the rules we need to install, iptables-service.

#### Step-5: Install the required packages like elinks, wget, git and curl packages.

![alt text](images/install-packages.PNG)

#### Step-6: Install bind, and bind-utils packages.

![alt text](images/bind-utils.PNG)
![alt text](images/bind-utils-quite-mode.PNG)

---

#### Step-7 : Install web server package

![alt text](images/web-server.PNG)

#### Step-8 : Install FTP server

![alt text](images/ftp-server.PNG)

#### Step-9 : Assign Static IP and Verification.

![alt text](images/assign-static-ip.PNG)

![alt text](images/verification-1.PNG)

#### Add entry into /etc/hosts file too.

![alt text](images/add-entry-in-hostfile.PNG)

#### Change the setting from NAT to Bridge for all the 3 VM-machines to communicate with each other.

![alt text](images/nat-to-bridge.PNG)

---

#### All Verifications By CLI (Command Line Interface) on DNS_Master

#### 1. Hostname

## ![alt text](images/master-dns-verification.PNG)

#### 2. SEStatus

## ![alt text](images/master-dns-verification_2.PNG)

#### 3. IfcfgEns file

## ![alt text](images/master-dns-verification_3.PNG)

#### 4. NAT bridging setting

## ![alt text](images/master-dns-verification_4.PNG)

#### 5. All package installation check.

## ![alt text](images/master-dns-verification_5.PNG)

#### 6. SELinux file configuration check

## ![alt text](images/master-dns-verification_6.PNG)

#### 7. httpd and ftp download package check

## ![alt text](images/master-dns-verification_7.PNG)
