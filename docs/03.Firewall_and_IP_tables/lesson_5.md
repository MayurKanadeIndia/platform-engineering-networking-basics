# Input Direction, for all services, Block Single Host, Network, Any IP

### Lab Setup Architecture

![alt text](images/lab_setup.png)

---

### Task 1:

#### Block all types of access to firewall from client11, that is from client11 we can not access anything on firewall.

- The client11 will not be able to access any services on the firewall (ssh,ftp,web,telnet server)

#### "we have to put the rule inside the firewall rule"

#### Rule:

## ![alt text](images/block_rule_iptables.PNG)

## ![alt text](images/block_task1_success.PNG)

#### To check the rule is applied perfectly or not, then we use the following command:

## ![alt text](images/iptables_policy_check.PNG)

### Verification:

## ![alt text](images/blocked_for_client11.PNG)

#### Checking connections from client31 machine

## ![alt text](images/verification_from_31_machine.PNG)

#### How to remove the applied rule again?

#### "Instead of typing -A we will replace it with -D (for dropping the rule)"

## ![alt text](images/delete_rule.PNG)

---

### Task 2:

#### Block all types of access to firewall from "172.24.0.0/16" network, that is from client11 and client31 we can not access anything on firewall.

## ![alt text](images/apply_rule_on_entire_network.PNG)

#### Checking the connection from client11 and client31 to the firewall.

## ![alt text](images/verification_from_client11_and_client31.PNG)

#### Verification from the Client c2 Machine going to be successful. It is a different network 192.168.0.0/24 and not the same 172.0.0.0/16 network.

## ![alt text](images/Verification_from_client_c2.PNG)

---

---

### Task 3:

#### Block all types of access to firewall from any ip, that is from "client11", "client31" or "c2" we can not access anything on firewall.

#### If you're not defining any source then it means, all inward traffic is blocked by firewall.

## ![alt text](images/block_all.PNG)

### Verification: All networks been blocked and no network can access the services on firewall.

## ![alt text](images/verification_from_all_networks_to_firewall.PNG)

#### to drop all the rules we use below command

## ![alt text](images/flush_rules.PNG)

---
