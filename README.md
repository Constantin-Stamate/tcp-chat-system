# TCP Chat System

This repository contains a complete Java-based TCP Chat System developed for laboratory exercises in
the **Network Programming Course** at **UTM (Technical University of Moldova)**. The project implements
a client-server architecture using TCP sockets and demonstrates real-time bidirectional communication,
multi-threaded server design, concurrent client handling, and safe resource management.

The system consists of:

- A multi-threaded TCP Chat Server
- A console-based TCP Chat Client

## System Architecture

The application follows a classic client-server model:

- The **Server** listens for incoming connections and manages multiple clients concurrently.
- The **Client** connects to the server and enables real-time message exchange.
- Messages sent by a client are broadcast to all connected clients.

Communication is implemented using Java `Socket` and `ServerSocket`.

## Server Features

- TCP Server initialization on port **65433**
- Multi-threaded client handling (one thread per client)
- Real-time message broadcasting
- Virtual IP assignment for connected users
- Username-to-IP mapping using synchronized collections
- Graceful shutdown mechanism
- Safe client disconnection handling

## Client Features

- TCP connection to the server (`127.0.0.1:65433`)
- Username registration upon connection
- Real-time message sending
- Dedicated thread for receiving broadcast messages
- Graceful exit command (`exit`)
- Proper socket and stream cleanup

## Concurrency & Synchronization

- Multi-threaded server architecture
- Dedicated client handler threads
- Separate reader thread on client side
- Synchronized collections for shared resources
- Volatile control flag for safe lifecycle management
- Exception handling for network and I/O failures

## Installation

1. **Clone the repository**

```bash
   git clone https://github.com/Constantin-Stamate/tcp-chat-system
```

2. **Navigate to the project directory**

```bash
   cd tcp-chat-system
```

3. **Navigate to the server project folder**

```bash
  cd chat-tcp-server
```

4. **Build the server project using Maven**

```bash
   mvn clean install
```

5. **Run the TCP chat server**

```bash
   java -cp target/classes org.tcpchat.server.Server
```

6. **Navigate to the client project folder**

```bash
  cd chat-tcp-client
```

7. **Build the client project using Maven**

```bash
   mvn clean install
```

8. **Run the TCP chat client**

```bash
   java -cp target/classes org.tcpchat.client.Client
```

## User Guide

To test and use the TCP Chat System, follow these steps:

- Start the server application first. The server begins listening on port 65433 and waits for client connections.
- Open two separate terminal windows and start two client applications.
- When prompted, enter a different username in each client.
- Once both clients are connected, type a message in one client and press Enter.
- The message is sent to the server.
- The server receives the message and broadcasts it to all connected clients.
- Both clients will display the message in real time.
- To disconnect a client, type `exit` in the client console. The client will close the connection gracefully.
- The server continues running and can accept new client connections.

## Technologies Used

- Programming Language: Java
- Networking: TCP Sockets
- Concurrency: Java Threads
- Build Tool: Maven
- IDE: IntelliJ IDEA

## Resources

For deeper understanding of the Transmission Control Protocol (TCP):

- [RFC 793 – Transmission Control Protocol Specification](https://datatracker.ietf.org/doc/html/rfc793) — the original
  official TCP protocol specification describing connection establishment, flow control, and reliability mechanisms.

- [RFC 9293 – Transmission Control Protocol (TCP) – Updated Specification](https://datatracker.ietf.org/doc/html/rfc9293) —
  the modern consolidated TCP specification that updates and replaces earlier RFC documents.

- [Cloudflare Learning – What is TCP?](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/) — a clear and
  practical explanation of how TCP works, including the three-way handshake, acknowledgments, and reliability features.

## Author

This project was developed as part of the **Network Programming Course** at **UTM (Technical University of Moldova)**.

- GitHub: [Constantin-Stamate](https://github.com/Constantin-Stamate)
- Email: constantinstamate.r@gmail.com