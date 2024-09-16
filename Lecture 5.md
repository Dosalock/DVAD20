****## Lecture 5 The SDN Data Plane

Data forwarding in SDN

Last time we started to look into SDN and today we will focus on one plane of the two planes (data/control) today is the data plane.

## Evolving Network Requirements

Several trends are driving network providers and users to reevaluate trad approaches to network archit.

* Deman is increasing
* Supply is increas
* Complex traffic patterns

## Limit of trad. networks by ONF

* The Open Network FOundation (ONF cites four general limits of trad. network archi.
  * Static, complex, unsuited for DCs
  * Inconsistent policies
    Har to implement across different providers
  * Inability to scale
  * Vendor dependenecy

## SDN APPROACH

**Insert slide mby**

adaptability

automation

maintainability

model management

mobility

integrated security

on-demand scaling

we should have models of networks, this neworks should work like this, have this properties, not have to go to each router individually.

## The Modern APproach to COmputing and Networking

Transform the vertical mainframe market to a horizontal marketplace

## SDN Equals Sepratation

Decoupling of control and data plane
Control plane operates several data switches dumb hardware
several 3rd parties who can make producs and drive down the price

## SDN Architecture

**Seems like cool slide to add**

## The data plane network device

* Control support function
  * nteracts with Sdn ctrl layer
  * communicates w the sdn via OpenFlow
* Data forwarding functions
  * Forwarding data flows
  * data flow processing is controlled by rules defined by SDN application

the whole data plane is hold together by the openflow specification

## OpenFlow Spec

* Specifies

  * Ctrl protocol between the SDN controller and the switch
  * parts of the data plane behaviour
* History

  * 2008: openflow.org org establish
  * 2009: openflow 1.0
  * 2011: openflow netword foundation established
  * 2015: openflow 1.5.1

1.5.1 newest version today, good for implementation with not many new versions

OFNF support various open source network projects who support the same goal, MiniNet as an example "ONOS?"

## The OpenFlow Enviroment

* An openflow enviroment compromises openflow controllers that communicate to one or more openflow switches
* all switches, routers, and other network devices to be managed by an SDN ctrlr must have a common logical architecture
* A standard, secure protocol is needed between the SDN controller and the network device eg transport layer security (TLS)

## OpenFlow switch

The openflow spec is not just protocal between the switches and controller, also dictates what goes inside the switches, **add slide pic**

ports, controller, *flow table*, group table, meter table, openflow channel (usually multiple controllers working in sync)

In an OF switch a Forward table a series of tables, flow tables
This decides if we need to send the packet to the next flow table or ready to go straight out the ports

* Ports
  * physical
  * logical
  * reserved
* Tables
  * FLow Table
  * Group Table
  * Meter Table

## OpenFlow Ports

openflow defines 3 ports

* Physical ports: THe physical ports are a switch - defined ports that correspond to a hardware interface of the switch e.g. 'eth1'
* Logical port: logical ports are higher-level abstractions that may be defined in the switch using non-OpenFlow methods, e.g. link aggregation groups, tunnels, loopback interfaces
* reserved ports: The reserved ports are defined by the OpenFlow specification, e.g., FLOOD and CONTROLLER

## Flows and Flow Tables

Its tricky, its no clear def

its intentional its just what the user wants it to be, its the user of the SDN network for decide
e.g. every packet that origins from a certain IP might be a flow, or a MAC adress range, its up to what you need it to be

You can differentiate between tcp and udp as different flows, and within those it might be FTP, HTTP in tcp flow and then RTP and DNS in the UDP


| Tabel 0 | Table 1 | Table 3    |
| --------- | --------- | ------------ |
| IP      | TCP     | FTP / HTTP |
|         | UDP     | RTP / DNS  |

* A flow is a sequence of packets between a source and desti that are recognized by the networks as related and are treaded in a uniform fashion
* A flow table matches incoming packets to a particular flow and specifies what functions will be performed on the packets

flow table is just a table


| Match                                 | instuctions  |
| --------------------------------------- | -------------- |
| if match do certain<br />instructions | do something |

## Simplified packet flow through one flow table

**slide image**

Options are like Match fields, priority, counters, Intructions
So inbetween the flow tables you can modify the packets with the use of the instructions

Very often you only use 1 flow table, v1 of openflow only had 1 actually
You can do alot with just one flow table, most of the packets will go through only one

proactive programming with the flowtables is hard, you need to prepopulate the tables with all possible packets that could ever come through and the tables get too huge

reactive population is easier with when a packets arrive with no match a process starts to handle this and make a match and instruction

## The OpenFlow Table Structure


| Match fields | Priortiy | Counters | Intstructions | Timeouts | Cookie | Flags |
| -------------- | ---------- | ---------- | --------------- | ---------- | -------- | ------- |


| col1 |   |   |   |   |   |   |   |   |   |   | col2 | col3 |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | ------ |
|      |   |   |   |   |   |   |   |   |   |   |      |      |
|      |   |   |   |   |   |   |   |   |   |   |      |      |

Get the slide image im too bad at the tables

Data forwarding in SDN

Last time we started to look into SDN and today we will focus on one plane of the two planes (data/control) today is the data plane.

## Evolving Network Requirements

Several trends are driving network providers and users to reevaluate trad approaches to network archit.

* Deman is increasing
* Supply is increas
* Complex traffic patterns

## Limit of trad. networks by ONF

* The Open Network FOundation (ONF cites four general limits of trad. network archi.
  * Static, complex, unsuited for DCs
  * Inconsistent policies
    Har to implement across different providers
  * Inability to scale
  * Vendor dependenecy

## SDN APPROACH

**Insert slide mby**

adaptability

automation

maintainability

model management

mobility

integrated security

on-demand scaling

we should have models of networks, this neworks should work like this, have this properties, not have to go to each router individually.

## The Modern APproach to COmputing and Networking

Transform the vertical mainframe market to a horizontal marketplace

## SDN Equals Sepratation

Decoupling of control and data plane
Control plane operates several data switches dumb hardware
several 3rd parties who can make producs and drive down the price

## SDN Architecture

**Seems like cool slide to add**

## The data plane network device

* Control support function
  * nteracts with Sdn ctrl layer
  * communicates w the sdn via OpenFlow
* Data forwarding functions
  * Forwarding data flows
  * data flow processing is controlled by rules defined by SDN application

the whole data plane is hold together by the openflow specification

## OpenFlow Spec

* Specifies

  * Ctrl protocol between the SDN controller and the switch
  * parts of the data plane behaviour
* History

  * 2008: openflow.org org establish
  * 2009: openflow 1.0
  * 2011: openflow netword foundation established
  * 2015: openflow 1.5.1

1.5.1 newest version today, good for implementation with not many new versions

OFNF support various open source network projects who support the same goal, MiniNet as an example "ONOS?"

## The OpenFlow Enviroment

* An openflow enviroment compromises openflow controllers that communicate to one or more openflow switches
* all switches, routers, and other network devices to be managed by an SDN ctrlr must have a common logical architecture
* A standard, secure protocol is needed between the SDN controller and the network device eg transport layer security (TLS)

## OpenFlow switch

The openflow spec is not just protocal between the switches and controller, also dictates what goes inside the switches, **add slide pic**

ports, controller, *flow table*, group table, meter table, openflow channel (usually multiple controllers working in sync)

In an OF switch a Forward table a series of tables, flow tables
This decides if we need to send the packet to the next flow table or ready to go straight out the ports

* Ports
  * physical
  * logical
  * reserved
* Tables
  * FLow Table
  * Group Table
  * Meter Table

## OpenFlow Ports

openflow defines 3 ports

* Physical ports: THe physical ports are a switch - defined ports that correspond to a hardware interface of the switch e.g. 'eth1'
* Logical port: logical ports are higher-level abstractions that may be defined in the switch using non-OpenFlow methods, e.g. link aggregation groups, tunnels, loopback interfaces
* reserved ports: The reserved ports are defined by the OpenFlow specification, e.g., FLOOD and CONTROLLER

## Flows and Flow Tables

Its tricky, its no clear def

its intentional its just what the user wants it to be, its the user of the SDN network for decide
e.g. every packet that origins from a certain IP might be a flow, or a MAC adress range, its up to what you need it to be

You can differentiate between tcp and udp as different flows, and within those it might be FTP, HTTP in tcp flow and then RTP and DNS in the UDP


| Tabel 0 | Table 1 | Table 3    |
| --------- | --------- | ------------ |
| IP      | TCP     | FTP / HTTP |
|         | UDP     | RTP / DNS  |

* A flow is a sequence of packets between a source and desti that are recognized by the networks as related and are treaded in a uniform fashion
* A flow table matches incoming packets to a particular flow and specifies what functions will be performed on the packets

flow table is just a table


| Match                                 | instuctions  |
| --------------------------------------- | -------------- |
| if match do certain<br />instructions | do something |

## Simplified packet flow through one flow table

**slide image**

Options are like Match fields, priority, counters, Intructions
So inbetween the flow tables you can modify the packets with the use of the instructions

Very often you only use 1 flow table, v1 of openflow only had 1 actually
You can do alot with just one flow table, most of the packets will go through only one

proactive programming with the flowtables is hard, you need to prepopulate the tables with all possible packets that could ever come through and the tables get too huge

reactive population is easier with when a packets arrive with no match a process starts to handle this and make a match and instruction

## The OpenFlow Table Structure


| Match fields | Priortiy | Counters | Intstructions | Timeouts | Cookie | Flags |
| -------------- | ---------- | ---------- | --------------- | ---------- | -------- | ------- |


| Ingr port | Egr port | Ethr SA | Ethr DA | IP port | IPv4 DA | IPv6 DA | TCP Src | TCP Dest | UDP Src | UDP Dest |
| ----------- | ---------- | --------- | --------- | --------- | --------- | --------- | --------- | ---------- | --------- | ---------- |

Get the slide image im too bad at the tables

The strength in the flow table is the pipeline, we talked about differentiating different type of flows.

## OpenFLow Table Pipeline - The Basics

A switch includes one or more flow tables, its always connected serially never in parallell (organized as a *pipeline*)

## Processing in a OpenFlow Switch - The basics

Openflow defines two processing stages:

* Ingress processing: always happens, beginning wiht table 0, and uses the identity of the input port
* Egress processing: is the processing that happens after the outputport is determined. It happens in the context of the output port. This stage is optional

**Nice slide image**

## Message, instruction, action, and action set

* **Message**: the packets communicated between the controller and the switches the controller ctrls
* **Instruction**: An instruction defines what happens when a packet corresponding to the match is received e.g. fo to a specified flow table, apply and action
* **Action**: An operation that acts on a packet, e.g. packet forwarding and modifications
* **Action set**: Only one type of instruction per category, every flow table might add an action to be added to the action set that gets executed at the end. its execution ordes is predetermined and not related to the order they happen. e.g. an action added in table 0 might be the last one to exectute in the action set.

## Message types

openflow supports three message types:

* Controller-to-Switch: Message that are initiaded by the controller and used to manage or inspect the state of the switch direcyly e.g. modifying the flow entry (OFPT_FLOW_MOD)
* Asynchronous: Messages that are initiaded by the switch and used to update the controller about network events and changes to the switch state e.g. incomping packet (OFPT_PACKET_IN)
* Symmetric: Messages that are initiated by either the switch or the controller without a preceding request e.g. hello and echo messages

## Instruction types

* Direct packet through the pipeline: The Goto-Table instructions directs the packet to a table farther alon gin the pipeline
* Perform action on a packet: THe Apply-actions instruction applies the specified actions immediately without changing the action set associated with this packet.
* Update action set: The Write-Actions instructions merges specified actions into this packets's current action set. The Clear-Actions instruction clears all the actions in the action set
* Update metadata: A metadata value can be associated with a packet. It is used to cary information from one table to the next. The Write-Metadata instructions updates an existing metadata value or creats a new value.

mostly see one type of action "Apply-Action"

## Action types

* Several type of actions e.g.
  * Outputport
  * set a field in a packet
  * push and pop tag field
  * change ttl

## Example #1: A simple hub

showing some example about how you make a hub with a SDN

match table looking like this


| Match | Instruction |
| ------- | ------------- | 
| ALL   | FLOOD       |      

