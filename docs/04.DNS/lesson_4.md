# DNS client machine setup.

#### Step-1 : Set hostname, disable firewalld and NetworkManager

![alt text](images/client-dns-step1.PNG)

#### Step-2: Disable SELinux

![alt text](images/client-dns-step2.PNG)

#### Step-3: Change the location and initial settings of "ifcfg-ens33" file

![alt text](images/client-dns-step3.PNG)

#### Step-4: Disable firewall policies

![alt text](images/client-dns-step4.PNG)

#### Step-5: Install Client DNS necessary packages

![alt text](images/client-dns-step5.PNG)

#### Step-6: Install only Bind-Utils package and do not install Bind package. Bind package installed only on Master and Slave.

![alt text](images/client-dns-step6.PNG)

#### Step-7: Assign Static IP Address

![alt text](images/client-dns-step7.PNG)

#### Step-8: Very Important Entry to add the address into /etc/hosts file.

![alt text](images/client-dns-step8.PNG)

#### Step-9: Change the network settings from NAT to Bridged

![alt text](images/client-dns-step9.PNG)

- Reboot the system to see the changes.

#### Step-10: Verify the static IP is assigned or not?

- The static IP will be set to the machine.
  ![alt text](images/client-dns-step10.PNG)

#### Step-11: Check the connectivity between Client machine to Master

![alt text](images/client-dns-step11.PNG)

---

#### DNS-Client Machine Verification through CLI

#### 1. Hostname

## ![alt text](images/dns-client-verification1.PNG)

---

#### 2. ifcfg ens33 file

## ![alt text](images/dns-client-verification2.PNG)

---

#### 3. SELinux Status

## ![alt text](images/dns-client-verification3.PNG)

---

#### 4. All Packages Installation check

## ![alt text](images/dns-client-verification4.PNG)

---

#### 5. PING to Master DNS check

## ![alt text](images/dns-client-verification5.PNG)
