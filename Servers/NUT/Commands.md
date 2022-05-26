# Commands

## Scan For UPS(s)

### Scan for USB connnected UPS
```
sudo nut-scanner -U
```

### Scan for SNMP connected UPS
```
sudo nut-scanner -S -s <IP>
```


## Restart All Services

```
sudo service nut-server restart
sudo service nut-client restart
sudo systemctl restart nut-monitor
sudo upsdrvctl stop
sudo upsdrvctl start
```
