processes communicate within a system
reasons for doing this:
- information sharing
- computation speedup
- modularity
- convenience

IPC can be done via message passing or shared memory

#### Passing:
- from client to server, or client to client
- small amounts of data
- simple

#### Shared Memory
- created and gain access to memory regions
- maximum speed and convenience of communication

Question: Distinguish between the client-server, known as C-S, and peer-to-peer, known as P-P, models of distributed systems

Answer: The C-S requests services that are provided by the S. while P-P is equal P can request and provide services – or both. A node may request a service from another P, or the node may in fact provide such a service to other peers in the system