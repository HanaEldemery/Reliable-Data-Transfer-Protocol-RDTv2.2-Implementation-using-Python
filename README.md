# Reliable Data Transfer Protocol RDTv2.2 Implementation using Python
In this project, I implemented the Reliable Data Transfer protocol version 2.2 (RDTv2.2). This protocol, a stop-and-wait protocol, utilizes positive acknowledgment with retransmission and an alternating bit scheme using a 1-bit sequence number to tolerate packet corruption. My implementation consisted of several key components: the sender, the receiver, and the network layer, which facilitated communication between the sender and receiver.
I started by modifying the provided skeleton code to develop the sender, receiver, and network layers necessary for the RDTv2.2 protocol. The main.py file served as the main script to initiate and test the protocol. I set up parameters such as the message to be sent, network reliability, delay, and corruption probabilities for packets and acknowledgments. The script created instances of the sender and network layer and initiated the sending process.
The sender.py file contained two primary classes: SenderProcess and RDTSender. The SenderProcess class managed the application layer’s outgoing data buffer, allowing me to set and retrieve the message to be sent. The RDTSender class handled the core functionality of the RDTv2.2 protocol. It initialized the sender’s sequence number, calculated checksums for data packets, created packets with sequence numbers and checksums, and sent these packets through the network layer. Additionally, the sender checked for corrupted acknowledgments and expected sequence numbers to ensure reliable data transfer.
In the receiver.py file, I implemented the ReceiverProcess and RDTReceiver classes. The ReceiverProcess class managed the application layer’s incoming data buffer, delivering received data to the application layer. The RDTReceiver class handled the reception of packets, checking for corruption and matching sequence numbers. Upon receiving a valid packet, the receiver delivered the data to the application layer and generated an acknowledgment packet to send back to the sender.
The network.py file provided the network layer that facilitated packet delivery between the sender and receiver. This layer introduced controlled packet corruption and delay to simulate real network conditions. The NetworkLayer class, included methods to corrupt packets and acknowledgments based on specified probabilities. It bridged the sender and receiver, ensuring that the sender’s packets reached the receiver and the receiver’s acknowledgments reached the sender.
To validate my implementation, I designed and executed several test cases, capturing screenshots of the results. The project report included detailed FSM diagrams for both the sender and receiver, pseudocode for the protocol, explanations of changes made to the skeleton code, and the results of my test cases. By thoroughly documenting my process and results, I ensured that my implementation met the project’s requirements and demonstrated the principles of reliable data transfer.
In summary, this project provided a comprehensive understanding of the RDTv2.2 protocol, reinforcing theoretical concepts through practical implementation. My work involved designing and testing a reliable data transfer system that could handle packet corruption, providing valuable insights into the challenges and solutions associated with network communication.
