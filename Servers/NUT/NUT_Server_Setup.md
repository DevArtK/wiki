# NUT Server Setup


## Setup
```
sudo apt install nut nut-client nut-server
sudo ap install snmp
```

#### Config Locations

Default Path : /usr/local/ups/etc
Debian : /etc/nut
Redhat + Derivatives : /etc/ups or /etc/upsd

#### Scan
```
sudo nut-server -S -s <IP>
```
Save output

```yaml
[nutdev1]
    driver = "snmp-ups"
    port = 192.168.1.203 # : 161
    mibs = "apcc"
    community = "public"
```

#### Config
Backup default configs :
- /etc/nut/ups.conf
    - Used to setup the driver (snmp) and the UPS communication

- /etc/nut/upsmon.conf
    - Used to setup monitors

- /etc/nut/upsd.conf
    - Used to specify where the service will listen on

- /etc/nut/nut.conf
    - Used to specify what mode NUT should run in

- /etc/nut/upsd.users
    - User(s) used to connect to get information from the UPS

####



## NUT Server
