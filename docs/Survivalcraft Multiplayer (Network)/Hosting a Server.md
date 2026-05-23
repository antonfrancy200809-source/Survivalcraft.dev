To host a server, first of all, you need to perform Port Forwarding for your server's port (which is generally 28887).

Port Forwarding is a necessary operation if you want to host a server from your computer and allow other players to connect from the outside.

### 1. Find your computer's IP address and your router's IP (windows)

Open the Command Prompt (on Windows, press `Windows + R`, type `cmd` and press Enter). Type the following command:
Look for these two pieces of information:
- **IPv4 Address**: your computer's address (e.g., `192.168.1.100`)
- **Default Gateway**: your router's address (e.g., `192.168.1.1`)


To prevent your IP from changing after a reboot, configure it as static:

1. Press `Windows + R`, type `ncpa.cpl` and press Enter.
2. Right-click on your active connection (Wi-Fi or Ethernet) → **Properties**.
3. Select **Internet Protocol Version 4 (TCP/IPv4)** → **Properties**.
4. Choose **Use the following IP address** and enter:
   - **IP address**: the IPv4 address you found earlier (e.g., `192.168.1.100`)
   - **Subnet mask**: `255.255.255.0`
   - **Default gateway**: your router's address (e.g., `192.168.1.1`)
5. Click **OK**.
   
 Open the port in Windows Firewall

1. Search the Start menu for "Windows Defender Firewall with Advanced Security" and open it.
2. In the left menu, click **Inbound Rules** → on the right, **New Rule...**.
3. Select **Port** → **Next**.
4. Choose **TCP** and in "Specific local ports" type your server's port (usually `28887`) → **Next**.
5. Select **Allow the connection** → **Next**.
6. Leave all boxes checked (Domain, Private, Public) → **Next**.
7. Give the rule a name (e.g., "Server Port") → **Finish**.

Configure Port Forwarding on your router

1. Open your browser and type your **Default Gateway** address (e.g., `192.168.1.1`).
2. Log in with your router's credentials (often `admin` / `admin` or `admin` / `password`; check the label on the device).
3. Look for the **Port Forwarding** section (it may also be called "Port Forwarding", "Virtual Server", or "NAT").
4. Add a new rule with the following details:
   - **Service name**: a name of your choice (e.g., "MyServer")
   - **External port**: `28887`
   - **Internal IP**: your computer's static IP address (e.g., `192.168.1.100`)
   - **Internal port**: `28887`
   - **Protocol**: `TCP` (or `TCP/UDP`)
