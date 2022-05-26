# SNMP - Simple Network Management Protocol

Standardized protocol used to collect and organize device information on a
network.

Does this over UDP port 161

A device that is SNMP enabled is known as an agent, who has several objects that
can be interacted with; some of which are an industry standard and some vender
specific.

Each object is assigned an OID



OID
: Object Identifier, anything and everything on a device can be monitored by SNMP has an OID

A sequence of numbers which at first glance look like an IP address

OIDs are stored in a file called a MIB

Example of an OID
```
1.3.6.1.2.1.2.2.1.8
```

MIB
: Management Information Base, a text file that allows us to translate
numberical OIDs to word based oids

The MIB file follows a tree structure
- Each level has a number associated to it, which correlates to the OID number,
  tells the exact location of the object

Example translateion of OID to MIB:
```
OID : 1.3.6.1.2.1.2.2.1.8 -> MIB : SYNOLOGY-SYSTEM-MIB::temperature.0
```

Don't have to use MIBs at all and just use OID, but MIBs make it alot easier

There are a number of standard OIDs and MIBs that are incorporated into most
SNMP implementations by default such as finding the uptime of a device with
```
sysuptime.0
```

## 2 Ways to use SNMP

### Polling
Network monitoring system connects to device on port 161, and tells the device
which OID it wants information on, device responds with the information to the
network montioring systems's port 161


### Notifying
Device sends OID related message to monitor system port 162
- These messages are known as either traps, notifications, or informs


### SNMP Versions
There are 3 versions of the SNMP protocol

**Version 1**
- No username required
- Use "community string"
- No encryption

**Version 2c**
- No username required
- Use "community string"
- No encryption

**Version 3**
- Most secured of the three versions
- Needs username + password
- Not all devices support version 3


## NMS - Network Management System

Software required to interact with the SNMP Agent

There are a few possible ways of the NMS to communicate with Agent

#### GET Requests

Get messages include Get, GetNext, GetBulk

Which are used to acttively request information from the agent

#### SET Requests
Set requests are used to change the value of SNMP object on the device


#### TRAP / INFORM
SNMP agents use traps and informs to actively communicate back toe the NMS,
which are useful for monitoring critical events

Informs are reliable in that they wait for an acknowledgement from the NMS,
 if it doesn't receive one it will send another

Traps are sent and forgotten
