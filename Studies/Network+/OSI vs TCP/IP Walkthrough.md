# OSI and TCP/IP Walkthrough


| OSI Layers       | TCP/IP Layers          |
| ---------------- | ---------------------- |
| 7 - Application  | 4 - Application        |
| 6 - Presentation |                        |
| 5 - Session      |                        |
| 4 - Transport    | 3 - Transport          |
| 3 - Network      | 2 - Internet           |
| 2 - Data Link    | 1 - Network Interface  |
| 1 - Physical     |                        |


## Recieving Walkthrough (Request)

### OSI Physical Layer + Data Link Layer & TCP/IP Network Interface Layer
> From the point of view of a network card


##### OSI Physical Layer & TCP/IP Network Interface Layer

*OSI Physical Layer*: is the actual physical cables that connect devices to provide internet

**OSI Data Link & TCP/IP Network Interface**

A *ethernet frame*<sup>1</sup> arrives at the network card

    [1]  **Ethernet Frame** : is a data link layers protocol data unit and uses the
    underlying ethernet  physical layer's transport mechanisms

    - Each Ethernet Frame starts with an Ethernet Header, which contains a
      destination and source MAC address as its first two fields
    - Middle section of the frame is payload data including any headers for other
      protocols carried in the frame
    - The frame ends with a frame check sequence(FCS) used to detect and in-transit
      corruption of data; 32-bit cyclic redundancy check

The first thing a network card does is check the MAC address if it is for that
destination

Checks the entire frame to see if it is okay, proceeds to strip off the MAC
address(es) off and the FCS, caching in memory the MAC address for a possible response
later

What is left is what is called and *IP Packet* <sup>2</sup>

#### OSI Network Layer & TCP/IP Internet Layer

This layer has two functions

1. Break up segments into network packets and reassembling the packets on the
   receiving end
2. Routing packets by discovering the best path across a physical network


#### OSI Transport & TCP/IP Transport Layers

Acts as the assembler and disassembler of data

- If there is alot of data to send or recieve it will break that data up into
seperate packets and when recieving assemble those packets

Port numbers in network packet get passed to next layer up


#### OSI Session + Presentation + Application & TCP/IP Application Layers

- **OSI Session Layer**: is designed to connect a server to a client on a remote
system

- **OSI Presentation Layer**: Basically no longer used as obscure filetypes are
  no longer used; was used to present data
  to the application layer in an accurate well defined and standardized way

- **OSI Application Layer**: This layer isn't talking about actual applications
  such as web browser, or email client for example. This layer has to do with
  the built in smarts that allows applicaitons to interface with a network
  Deals with port numbers; the recieving port number and the return port number



## Sending Walkthrough (Response)

#### Application + Presentation + Session OSI Layers & TCP/IP Application Layers

Starting with some data, and will be sending out an ethernet frame
- Individual application sends data to the Application Layer; will also be adding
  the port that the ethernet frame will be coming from and the port it
  will be sending to(from the incoming frame)

#### OSI + TCP/IP Transport Layers

Will be breaking that data up and providing sequencing numbers to the broken up
IP packets, combining with the sending & recieving ports

#### OSI Network layer & TCP/IP Internet Layer

Will take the IP infromation that it recieved from the original incoming data
and will reverse the order sending IP will now be recieiving IP and append that
to the IP packet


#### OSI Data Link + Physical Layers + TCP/Ip Network Interface Layers

Will take the IP packet from the Network/Internet Layer and appends the MAC
Addresses and runs another FCS (Frame Check Sequence).
At this point the IP packet gets sent out
