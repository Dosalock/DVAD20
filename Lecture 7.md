# Lecture 7


# The SDN Controller

everything thats supposed to be in a router is controlled there
calc shortest path is e.g. made by the SDN controller

needs interfaces between the application and transport layer

connected to east and westbound something?

## The concept of a NOS

the sdn controller is able to provide and operating system to the transport layer

takes care about how things get done but the application takes care of what should be done

## The SDN Controller Interfaces

SDN Controller interfaces have east and westbound interfaces (SDNi)

# Ryu SDN Controller

* A component-based, OS SDN ctrl written in Python
* Ryu supposrts various protocols for managing networl devices i.e. the soundbound interface)
  * OpenFlow
  * OVSDB
  * BGP

# Archit. of Ryu framewrk

Pic from slides 136

# Basic Ryu Ctrl CmdLine options

* To obtain avail opts: ryu_manager -help
* To run a Ryu app: ryu_manager <app.py>
* Enable debug: ryu_manager -verbose
* Stop app: CTRL-C

# NOX & POX

* NOX
  * the first OpenFlow Controller written in C++
  * Two lines of dev: NOX classic and (new) NOX
    * NOX-Classic supports C++ and Python development
    * (new) NOX is faster than NOX-Classic but only supports C++
* POX
  * Python version of NOX
  * Targets research (not production)
  * No stable API

# OpenDaylight

* Founded 2013
* Very popular SDN Controller
* ODL is a Linux foundation collaborative Project

cont'd

mostly graphics from slides page 145

# ONOS

* Open Network Operating System
  * Founded 2012
  * ONOS is a linux collab
  * written for telco applications (distributed)
  * supports p4

# Inter-Domain Routing with ONOS

* ONOS implements both intra-domain/cluster and inter-domain/cluster communication
*
