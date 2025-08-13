Task 4 – Setup and Use a Firewall on Linux (UFW)

Objective
Configure and test basic firewall rules to allow or block network traffic using **UFW** on Linux. Demonstrate blocking and allowing Telnet (port 23) as an example.

---

Steps Performed

1. Install UFW**
```bash
sudo apt update
sudo apt install ufw -y

sudo ufw enable
sudo ufw status numbered

Install and Start Telnet Server
sudo apt install telnetd -y
sudo systemctl enable inetutils-inetd
sudo systemctl start inetutils-inetd

sudo ss -tulnp | grep :23

telnet localhost 23

Block Telnet using UFW
sudo ufw deny 23/tcp
sudo ufw status numbered

Test Telnet Connection (Allowed)
telnet localhost 23

sudo ufw delete deny 23/tcp
sudo ufw allow 23/tcp
sudo ufw status numbered

telnet localhost 23

Final Cleanup
sudo ufw delete allow 23/tcp

