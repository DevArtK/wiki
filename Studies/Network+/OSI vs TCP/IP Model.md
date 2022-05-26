# OSI vs TCP/IP Models Overview

*OSI* is the old model
*TCP/IP* is the new modern model

## OSI 7 Layer Model

The OSI Model helps in making inter-connectivity work

In this model, there are 7 distinct functions that a network must do:

##### **OSI Model**
| Layer | Name         |
| ---   | ---          |
| 7     | Application  |
| 6     | Presentation |
| 5     | Session      |
| 4     | Transport    |
| 3     | Network      |
| 2     | Data Link    |
| 1     | Physical     |

*Physical Layer*
> Physical connections, wiring, etc


*Data Link Layer*
> Anything that works with a MAC address works at the Data Link Layer
ie: Network cards, switches, etc


*Network Layer*
> Has to do with logical addresses
ie IP addresses, routers


*Transport Layer*
> Assembly/Disassemly area for data, since data is large and the data that goes
through a network are relatively small. As it gets broken down into individual
packets and in the right order

*Session Layer*
> The actual connection between two systems. What kind of connection is it (such
as TCP between a web server and a web client). Defines what's taking place in
terms of connectivity

*Presentation Layer*
> Used to convert data that applications can read, has to do with what form of
data is being transferred and translating to be readable, used for deliver and
formatting of information to the application layer

*Application Layer*
> The smarts in the applications that make the network aware; Interface that
directly interacts with the application and provides common web application
services (APIs)


## TCP/IP Model
In this model, there are 4 functions that a network must do:

- How it differs from OSI is that it combines some layers together to from a
single common function


| Layer | Name              |
| ---   | ---               |
| 4     | Applicaiton       |
| 3     | Transport         |
| 2     | Internet          |
| 1     | Network Interface |

*Network Interface* : Similiar to Data Link & Physical Layers in OSI
> Covers Physical cables, MAC addresses, Network cards, everything in terms of
hardware, except a few exceptins such as routers


*Internet*
> IP addresses, routers

*Transport*
Assembly & Disassembly as well as what it takes to connect to another system so
that the data gets there, ie TCP/UDP

*Application*
Takes in the OSI's Application, Presentation and Sessions Layers and puts them
into its own Application Layer. TCP/IP Model looks at the Application Layer as
appicaitons
