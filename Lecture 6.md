# Lecture 6 The SDN Control Plane

## The SDN Architecture

## The SDN Controller

* Maps application layer service requests into specific commands and directives to data plane switches and supplies applications wiht information about data plane topology and activity
* The functionality provided by the SDN controller can be viewed as a network operating system

## The Concept of a Network Operating System

* The functionality provided byt the SDN controller can be viewed as a *Network Operating System*(NOS)
* A NOS provides essential services, common application programming interfaces (APIs), and abstraction of lower-layer elements to developers
* The functions of an SDN NOS enable developers to define network policies and manage networks without concern for the details of the network device characteristics

## The SDN Controller Interfaces

## The Ryu SDN Controller

* A component-based, open-source SDN controller written in Python
* Ryu originates from a Japanese workd meaning "flow"
* Ryu suppoerts various protocols for managing network devices (i.e., the southbound interface), e.g.,
  * OpenFlow
  * OVSDB
  * BGP

## The Architecture of the Ryu Framework

## Basic Ryu Controller Command Line Options

## The Functional Architecture of a Ryu Application

## Examples of Common OpenFlow Controllers

## NOX and POX

## OpenDaylight

## ONOS

## Cooperation and Coordination between Controllers

## The SDN Domain Structure

## Federated SDN Networks

## Routing Beyond an SDN Controller's Domain

## Inter-domain Routing with OpenDaylight

## Inter-domain Routing with ONOS
