# Key Characteristics of Distributed Systems

1. Scalability
2. Reliability
3. Availability
4. Efficiency
5. Servicability or Manageability

## Scalability

Vertical scaling is moving from smaller machine to bigger machine. Horizontal scaling is adding a machine.

Vertical scaling needs a downtime in order to be performed

## Reliability

By definition, reliability is the probability a system will fail in a given period. It is considered reliable if it keeps delivering (live).

It is usually achieved by redundancy and obviously redundancy has a cost.

## Availability

Availability is the time a system is operational. If an aircraft is down for maintenance, it is considered not available during that time. An aircraft that can make it through any possible weather safely is more
reliable than one that has vulnerabilities to possible conditions.

If a system is reliable it is availalbe. But other way is not true.

## Efficiency

Two standard measures of efficiency are the response time that denotes the delay to obtain the first item and the throughput which denotes the number of items delivered in a given time unit.

1. Latency
2. Throughput

The two measure correspond to the following unit costs:

- Number of messages globally sent by the nodes of the system regradless of the message size.
- Size of messages represnting the volume of data exchanges.

But if we to say number of messages measures efficiency is too simplistic. Therfore we just have to do robust estimates


## Serviceability or Manageability

It's a measure of how easy to maintain/fix the system.

If it's not manageable, then it affects availability because it will require more downtime to fix the system
