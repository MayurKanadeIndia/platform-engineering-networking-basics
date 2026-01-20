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

![alt text](images/blocked_for_client11.PNG)

---
