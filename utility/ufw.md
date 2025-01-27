# command: ufw

uncomplicated firewall

```bash
systemctl status ufw # checking status of firewall

ufw allow [IN/OUT] [PORT]/[PROTOCOL] # protocol = tcp/udp
ufw allow [IN/OUT] [APPLICATION LAYER PROTO] # = http q/ smtp
```