
  
   1. In a few sentences, describe the general architecture of your interface monitor. [1 mark]


TODO











    2. In a few sentences, describe the general architecture of your network monitor. [1 mark]

TODO












    3. Could the interface monitor and network monitor all be contained within one process, if so how?[1 mark]

This could be done with threads, where each monitor would get it's own thread, running in parallel with other processes.




    4. Could the interface monitor and network monitor all be contained within one process, assuming 128 network interfaces running at several Giga-bits per second, which require a polling interval of one millisecond per interface. [1 mark]

There is no hard limit on the amount of threads that could be created. Potentially interface monitors could even run on GPU.
One process could also have multiple sockets, so this may be desired. Pole function takes microseconds as its's parameters.




    5. What is a software defined network? In doing so, describe the applications layer, the control layer, and the forwarding layer. [2 marks]

SDN open and programmable network designed to handle packets received over network. 

Usually network relies mostly on the hardware like routers. Using SDN on top of that, allows to add more layers to the networking,  sorting packets by types and handling them more efficiently.

SDN has 3 layers:

1.Forwarding Devices: (forwarding layer) receive packets, take actions (dropping, sending packets or modifying headers on packets), updates counters

2.Network Operating System(control layer): has core services that interface with network nodes, and provide programmable interface for the network interfaces

3.Network Applications(application layer): handle packets, network focused actions

Packet flow: Forwarding device would parse header of the packet, and then (if needed) query Network OS to determine action on the packet for forwarding to the desired network application.
