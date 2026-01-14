# How to configure Networking?

#### If we want to put any machine into the network then following 4 things must be carried out.

#### In Windows System

- IP Address
- Subnet Mask
- Name of the machine
- Workgroup (A network in which, group of machines are resided.)

#### In a workgroup:

- All computers are peers; no computer has control over another computer.
- Each computer has a set of user accounts. To log on to any computer in the workgroup, you must have an account on that computer.
- There are typically no more than twenty computers.
- A workgroup is not protected by a password.
- All computers must be on the same local network or subnet.

---

# Configuring Two Windows Machines in the Same Workgroup and Network

- In this article, we'll walk through the process of setting up two Windows machines (let's call them Machine A and Machine B) to communicate over a local network using static IP addresses within the same subnet. This setup is ideal for small home or office environments where you want to share files, printers, or other resources without relying on a DHCP server. We'll use the following IP configurations:

- Machine A: IP Address = 172.24.1.10, Subnet Mask = 255.255.0.0
- Machine B: IP Address = 172.24.2.20, Subnet Mask = 255.255.0.0

- These addresses fall within the private IPv4 range (172.16.0.0 to 172.31.255.255), specifically in the 172.24.0.0/16 subnet, allowing direct communication without a router or gateway for basic testing. We'll also configure both machines to join the same workgroup (named "HOMENETWORK" for this example) to enable resource sharing. Finally, we'll test connectivity using the Ping command.
- This guide assumes you're using Windows 10 or 11 (the process is similar across recent versions), and the machines are physically connected via Ethernet cables (e.g., directly with a crossover cable or through a switch/hub). Ensure both machines are powered on and connected to the network before starting. Administrative privileges are required for these changes.

### Step 1: Configuring the IP Address and Subnet Mask on Each Machine

- Static IP configuration ensures reliable addressing. We'll disable IPv6 for simplicity (as it's not needed here) and focus on IPv4.
  On Machine A (IP: 172.24.1.10):

- Right-click the Start button (Windows icon) and select Settings (gear icon). Alternatively, press Windows key + I to open Settings directly.
- In Settings, navigate to Network & Internet.
- Click on Ethernet (or Wi-Fi if using wireless, though Ethernet is recommended for stability).
- Under the active connection (e.g., "Ethernet"), click Properties.
- In the Properties window, scroll down to the "IP settings" section and click Edit next to "IP assignment" (it might say "Automatic (DHCP)" by default).
- Change the dropdown from "Automatic (DHCP)" to Manual.
- Toggle on IPv4 (ensure IPv6 is toggled off if you want to simplify).
- Enter the following details:
  IP address: 172.24.1.10
  Subnet mask: 255.255.0.0 (this will auto-populate as "16" for subnet prefix length).
  Gateway: Leave blank (no default gateway needed for local subnet communication).
  Preferred DNS server: Leave blank or set to 8.8.8.8 (Google DNS) if internet access is desired later.
  Alternate DNS server: Leave blank or set to 8.8.4.4.

- Click Save to apply the changes. Windows may briefly disconnect and reconnect the network.

- To verify, open Command Prompt (search for "cmd" in the Start menu) and type ipconfig. Look under "Ethernet adapter Ethernet" (or similar) for "IPv4 Address" to confirm it's set to 172.24.1.10 with subnet mask 255.255.0.0.

---

### On Machine B (IP: 172.24.2.20):

Follow the exact same steps as above, but use these details in Step 8:

- IP address: 172.24.2.20
- Subnet mask: 255.255.0.0
- Gateway and DNS: Leave blank or configure as needed.

- After configuration, both machines should now be on the same logical network, allowing packet exchange.

##### Step 2: Setting the Workgroup Name on Each Machine

#### Workgroups allow Windows machines to discover each other for file sharing. By default, Windows uses "WORKGROUP," but we'll change it to "HOMENETWORK" for both to ensure they're in the same group.

### On Machine A:

- Right-click the Start button and select System.
- In the System window, click About on the left sidebar, then scroll down and click Advanced system settings (under "Related settings").
- In the System Properties window, switch to the Computer Name tab.
- Click the Change button next to "To rename this computer or change its domain or workgroup."
- In the Computer Name/Domain Changes window, under "Member of," select Workgroup (if not already selected).
- Enter HOMENETWORK in the Workgroup field (case-insensitive, but use all caps for consistency).
  Click OK. You'll see a welcome message for the new workgroup.
- Restart the machine when prompted (click OK and then Restart Now).

### On Machine B:

- Repeat the exact same steps, entering HOMENETWORK as the workgroup name, and restart.
- After rebooting both machines, they should now be visible to each other in Network Explorer (open File Explorer > Network). If not, ensure Windows Firewall allows File and Printer Sharing (go to Settings > Network & Internet > Ethernet > Properties > IPv4 > Advanced > WINS tab, but usually not needed for basic ping).

---

### Step 3: Testing Connectivity with the Ping Command

- Ping uses ICMP echo requests to verify if one machine can reach the other, confirming network configuration.

##### On Machine A (Testing Reachability to Machine B):

- Open Command Prompt (search "cmd" in Start menu).
  Type the following command and press Enter:
  ping 172.24.2.20
- Observe the output. A successful ping looks like this:
  ![alt text](images/ping_output.PNG)

- If you see "Reply from..." with low latency (e.g., <1ms), the connection is successful.
- If you get "Request timed out" or "Destination host unreachable," check cables, firewall (temporarily disable via Settings > Update & Security > Windows Security > Firewall & network protection), or re-verify IP settings.

### On Machine B (Testing Reachability to Machine A):

- Open Command Prompt.
- Type: ping 172.24.1.10
- Check for successful replies as above.

#### If both pings succeed bidirectionally, your setup is complete. You can now proceed to share folders (right-click a folder > Properties > Sharing tab) or use other network features.

#### Note: The main purpose to have two or more computers within a same network is to share the resources and nothing else.
