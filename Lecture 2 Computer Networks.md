## Computer Networks the Fundamentals

**Date 2024-09-02**

Brief recap on computer networks, should not be news to anyone

## What is Data Networking?

Its shuffling data from one computer to another.
A system of hardware, software, and protocols used to move data from one device to another.
Started because of resource sharing, we need to share information with eachother, also resources like hardware.
Just like humans the computers and data centers need to communicate with eachother. Much more efficient to make paths for the data instead of deliviring tapes or drives and alike. Right now computer networks is used for humans to communicate but seems to be more and more computers communicating with eachother. Mobile networks are starting to become a part of what we call internet, we expect to be able to surf the web when we connect to a cell tower or a wifi on the go.

When we talk about CN people seem to recall the layering concept.

## Protocol Layering and Encapsulation


| Layer 5               |                       | Layer 5               |
| ----------------------- | ----------------------- | ----------------------- |
| Layer 4               |                       | Layer 4               |
| Layer 3               |                       | Layer 3               |
| Layer 2               |                       | Layer 2               |
| Layer 1               |                       | Layer 1               |
| Physical-<br />Medium | Physical-<br />medium | Physical-<br />medium |

The layer have interfaces between each layer
theres a layer between 3 and 4, the same is true for 4 and 5....
The layers cannot access everything of the top and bottom layer, its an api in a sense.
The data sent through the layers have no idea what theyre sending other than the data of where and how to get it to the other layer.
You send the message with a new header and/or tail to intruct the next layer of what to do, the payload itself is untouched until it arrives.

## Protocol Reference Models

![](assets/20240902_134355_stack.png)

The OSI model is often used as a principel in text books but the networks that should use this model instead of the tcp/ip one often fail to do so.
OSI distinguishes how different nodes in the network talks to eachother and with what protocol, "host-router protocol"
Very well defined separation between the layer in between the layers, the tcp model can easily muddy up the difference between the implementation

OSI failed with having a bit too many layers
The session layer was introduced to decide who talks first and in what order ex. token exchange.
Presentation layer was supposed to introduced different formats to use in the packet.

Application layer is the application specific protocols, ex http for webbrowsers or SMTP. POP for email.

TCP/IP
Designed the other way to the OSI, OSI designed from ground up where TCP/IP started out with people hacking together things needed for the layer.
After some time it was decided physical layer was not to be part of the TCP/IP model but mostly for necessity cause IEEE handles physical products which the group designing TCP/IP does not.
TCP decided to let application layer handle these session and presentation layers to "simplifiy".
This stack is very generic and immesnly easier to develop around compared to the OSI model.

Mentions "The Elephant model" acceptance, doesnt seem to be the real name need to see later.

![](assets/20240902_133901_634457d032fc08095adf8506_Change_curve.png)

## Layer 1 - The Physical Layer

No protocols at this layer but cabling and network cards must adhere to sets of standards and criteria ex.

* Voltages
* Speeds
* Wiring

## Layer 2 - The (Data) Link Layer

First layer we see something resembling protocol

the logical link layer that takes care of the framing part, how do i send from one adress to another.

[A] ---- [B]
Two connected nodes in the datalink layer with "nothing" in between.
Could be physical repeaters or hubs and alike so we need adressing like MAC adress to handle who and where its going to and from.

* Responsibilites
  * Framing
    * The physical layer there isnt a concept of a packet, its not until you get to data link layer you get something resembling that which is called framing.
  * Error COntrol
  * Flow Control
    * if two super computers talk to eachother but theres a normal pc inbetween its the bottle neck this is congestion and not flow control
    * **FEC** Forward Error Correction, you can repair the message if some packages are lost on the way
    * **ARQ** Automatic Repeat Request, if something goes wrong you timeout and ask for the data to be sent again.
  * Adressing

Media Access Conrol (MAC)
Not always needed if you example have two ways for the data to flow, like a road. MAC is used to handle when things get sent and without collisions
**CSMA/CD** handles collisions, waits for enough time of silence before sending

## MAC Adresses

* Identifies a device on a local network
* a 48-Bit hexadecimal number
* Also called physical or burnt-in adresses
  * This is provided by the hardware manufacturer of example the network card.

Many times today we dont need this coliision control devices.

* Classic Ethernet
* Switched Ethernet
  * Learns what port a node is on unlike hubs
    * First message is broadcasted like a hub but then builds a table when the packets arrive to the recipient "learning switch"

## Switching Basics

Here we are forwarding things only using their physical adresses (MAC) and they dont know what the concept of IP adresses are.

* Allows us to interconnect links
* A Multi-Input/output, device
* Can connect switches to each other and hosts
* Each port is a separate *collision domain*

## The spanning tree protocol

Without this a ARP request can be looped forever when it tries to find the nodes of the network
This protocol makes a tree without any cycles to prevent these loops

* Prevents a packet from cirulating switches
* How the Spanning Tree Protocol or STP works
  * Executed at startup
  * Distributed algorithm
    * Each switch runs STP independently
    * No central coordination
  * Guaranteed to converge quickly
  * No data packets will be forwarded until STP finishes

![](assets/20240902_140506_STP.png)
