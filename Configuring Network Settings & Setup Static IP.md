# Configuring Network Settings
# Windows Server

1. Open **Server Manager**.
2. Click on **Local Server** in the left pane.
3. Under "Properties" in the right pane, click on the network adapter status (e.g., "Ethernet").
4. In the adapter properties, select "**Internet Protocol Version 4 (TCP/IPv4)**" and click "**Properties**."
5. Choose "**Use the following IP address**" and enter the static IP, subnet mask, and default gateway.

   - IP address: 192.168.1.2
   - Subnet mask: 255.255.255.0
   - Default gateway: 192.168.1.1

6. Click "**OK**" to save the settings.
7. Restart the network adapter or server if necessary.

# Windows 10 Client

1. Open the **Settings** app.
2. Go to "**Network & Internet**" and select "**Wi-Fi**" or "**Ethernet**" on the left.
3. Click on "**Change adapter options**."
4. Right-click on your active network connection and select "**Properties**."
5. Scroll down and select "**Internet Protocol Version 4 (TCP/IPv4)**" and click "**Properties**."
6. Choose "**Use the following IP address**" and enter the static IP, subnet mask, and default gateway.

   - IP address: 192.168.1.3
   - Subnet mask: 255.255.255.0
   - Default gateway: 192.168.1.1

7. Click "**OK**" to save the settings.
8. Restart the network adapter or the Windows 10 machine if necessary.

# Linux (Ubuntu)

1. Open a terminal.
2. Edit the network configuration file:

   ```bash
   sudo nano /etc/network/interfaces
3. Find the section for your network interface (e.g., ens33) and add or modify the following lines:

    ```bash
    auto ens33
    iface ens33 inet static
    address 192.168.1.4
    netmask 255.255.255.0
    gateway 192.168.1.1
4. Save the file and exit.
5. Restart the network service:
    ```bash
    sudo systemctl restart networking
# Ping Each Machine**

1. Open a command prompt or terminal on each machine.
2. Use the `ping` command to check connectivity:
    * On Windows and Linux:
        ```
        ping 192.168.1.2 # Replace with the IP address of the Windows Server
        ping 192.168.1.3 # Replace with the IP address of the Windows 10 client
        ```
    * On Windows Server:
        ```
        ping 192.168.1.4 # Replace with the IP address of the Linux machine
        ping 192.168.1.3 # Replace with the IP address of the Windows 10 client
        ```
    * On Windows 10:
        ```
        ping 192.168.1.2 # Replace with the IP address of the Windows Server
        ping 192.168.1.4 # Replace with the IP address of the Linux machine
3. If you receive replies, it means that the machines can communicate with each other.

**Note:** Ensure the firewalls on each machine allow ICMP traffic (ping) for successful communication.


