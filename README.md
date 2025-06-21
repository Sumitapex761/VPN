# VPN


✅ VPN Lab ✅
🖥️ Part 1: On Debian Server
1. Install OpenVPN
bash
Copy code
sudo apt update  
sudo apt install openvpn -y
2. Create config file
bash
Copy code
sudo nano /etc/openvpn/server.conf
Content paste:

nginx
Copy code
proto udp  
port 1194  
dev tun  
auth none  
cipher none  
ifconfig 10.8.0.1 10.8.0.2  
verb 3
3. Start server
bash
Copy code
sudo openvpn /etc/openvpn/server.conf
🪟 Part 2: On Windows Client
Step 1: Install OpenVPN GUI (Windows)
Download from:
https://openvpn.net/community-downloads/

Install in default location:
C:\Program Files\OpenVPN

Step 2: Open Notepad as Administrator
Paste this:

nginx
Copy code
remote 192.168.1.197  
proto udp  
port 1194  
dev tun  
auth none  
cipher none  
ifconfig 10.8.0.2 10.8.0.1
Save as:

arduino
Copy code
C:\Program Files\OpenVPN\config\client.ovpn
🧪 Step 3: Verify Connection
Open Command Prompt:

bash
Copy code
ping 10.8.0.1
If reply comes = tunnel working ✅

You can also ping:

bash
Copy code
ping 192.168.1.197
