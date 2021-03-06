# C-HTTP-Server

## Background information

###### HTTP
>HTTP is a protocol for fetching resources such as HTML documents. It is the foundation of any data exchange on the Web and it is a client-server protocol, which means requests are initiated by the recipient, usually the Web browser. A complete document is reconstructed from the different sub-documents fetched, for instance, text, layout description, images, videos, scripts, and more. 

###### OSI
>The Open Systems Interconnection model (OSI model) is a conceptual model that characterizes and standardizes the communication functions of a telecommunication or computing system without regard to its underlying internal structure and technology. Its goal is the interoperability of diverse communication systems with standard protocols. The model partitions a communication system into abstraction layers. The original version of the model defined seven layers.

The 4th layer: Transport Layer, is where HTTP is implemented.

###### Transport Layer
>The Transport layer is primarily responsible for ensuring that data is transferred from one point to another reliably and without errors. For example, the Transport layer makes sure data are sent and received in the correct sequence. The Transport layer provides flow control and error handling, and participates in solving problems concerned with the transmission and reception of packets. Common examples of Transport layer protocols are Transmission Control Protocol (TCP), User Datagram Protocol (UDP) and Sequenced Packet Exchange (SPX).

###### RFC 2616
>HTTP communication usually takes place over TCP/IP connections. The default port is TCP 80, but other ports can be used. This does not preclude HTTP from being implemented on top of any other protocol on the Internet, or on other networks. HTTP only presumes a reliable transport; any protocol that provides such guarantees can be used; the mapping of the HTTP/1.1 request and response structures onto the transport data units of the protocol in question is outside the scope of this specification.

## Implementing TCP

The code will be intended for UNIX-based systems

###### Socket
>A socket is the mechanism that most popular operating systems provide to give programs access to the network. It allows messages to be sent and received between applications (unrelated processes) on different networked machines. The sockets mechanism has been created to be independent of any specific type of network. IP, however, is by far the most dominant network and the most popular use of sockets

1. Create the socket
2. Identify the socket
3. Wait for incoming connection (server)
4. Send and receive messages 
5. Close the socket

## Building

```bash
gcc server.c -o server
gcc client.c -o client
./server
./client
```

```output
$ ./server

+++++++ Waiting for new connection ++++++++

Hello from client
------------------Hello message sent-------------------

+++++++ Waiting for new connection ++++++++
```

```
$ ./client
Hello message sent
Hello from server
```