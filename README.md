✅ VPN Lab ✅

1. Install OpenVPN

sudo apt update  
sudo apt install openvpn -y

2. Create config file
sudo nano /etc/openvpn/server.conf

Content paste:

proto udp  
port 1194  
dev tun  
auth none  
cipher none  
ifconfig 10.8.0.1 10.8.0.2  
verb 3


3. Start server

sudo openvpn /etc/openvpn/server.conf



🪟 Part 2: On Windows Client
📥 Step 1: Install OpenVPN GUI (Windows)
Download from: https://openvpn.net/community-downloads/

Install it (default location: C:\Program Files\OpenVPN)

📁 Step 2: open notepad as administrator 

Paste this:

remote 192.168.1.197    # Replace 192.168.1.197 with your Debian server's IP
proto udp
port 1194
dev tun
auth none
cipher none
ifconfig 10.8.0.2 10.8.0.1


🧪 Step 4: Verify Connection
Open Command Prompt in Windows:

ping 10.8.0.1

If reply comes = tunnel working ✅
You can also ping:

ping 192.168.1.197
