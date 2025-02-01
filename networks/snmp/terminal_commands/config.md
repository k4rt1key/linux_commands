# snmp config
```bash
sudo apt update && sudo apt install snmp snmpd -y
sudo nano /etc/snmp/snmpd.conf
sudo systemctl 
sudo systemctl status snmpd
sudo systemctl restart snmpd
sudo systemctl enable snmpd
sudo ufw allow 161/udp
sudo netstat -tulnp  | grep snmpd
```

## Config file for keeping my pc as agent

```bash
# /etc/snmp/snmpd.config
sysLocation    Sitting on the Dock of the Bay
sysContact     Me <me@example.org>
sysServices    72
agentaddress  udp:161,udp6:[::1]:161

view   systemonly  included   .1.3.6.1.2.1.1
view   systemonly  included   .1.3.6.1.2.1.25.1
view   systemview  included   .1.3.6.1.2.1.1

rocommunity public 10.20.40.0/22
rouser authPrivUser authpriv -V systemonly
```