# DNS Slave Server Setup

#### Step-1: The Slave setup, set hostname, disable firewall and NetworkManager

![alt text](images/slave-step-1.PNG)

- By default machine was set as @master but later on we have changed it to the slave.

#### Step-2: The SELinux Policy changed from enforcing to disabled.

![alt text](images/slave-step-2.PNG)

- By default the network settings is NAT

#### Step-3: Location and Initial settings of ifconfig-ens33 file.

![alt text](images/slave-step-3.PNG)

#### Step-4: Disable all firewall settings.

![alt text](images/slave-step-4.PNG)

#### Step-5: Install All the necessary packages.

![alt text](images/slave-step-5.PNG)

#### Step-6: Install Bind and Bind-Utils

![alt text](images/slave-step-6.PNG)

#### Step-7: Assign Static IP Address

![alt text](images/slave-step-7.PNG)

#### Step-8: Very Important change, make changes in /etc/hosts file.

![alt text](images/slave-step-8.PNG)

#### Step-9: Change Network setting from NAT to Bridge for the communication.

![alt text](images/slave-step-9.PNG)

- Reboot the system to see the changes.

#### Step-10: Verification from Slave to Master Connectivity.

![alt text](images/slave-step-10.PNG)
