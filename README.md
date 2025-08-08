Ex.No:1a – Study of Socket Programming
Aim:
To perform a study on Socket Programming using Python.

Introduction:
Socket programming is a crucial aspect of network communication, allowing data exchange between computers over a network. It forms the backbone of various networked applications, enabling communication between clients and servers. This study explores the fundamental concepts of socket programming, its use cases, and provides a practical example to demonstrate its implementation using Python.

Understanding Socket Programming:
Socket programming involves the use of sockets, which serve as endpoints for communication. A socket is identified by an IP address and a port number and facilitates data transfer between a client and a server. The two main types of sockets are:

Stream Sockets (TCP) – reliable, connection-oriented.

Datagram Sockets (UDP) – connectionless, faster but less reliable.

Key Concepts in Socket Programming:
1. Sockets
A socket is a software representation of a communication endpoint.

It is identified by an IP address and a port number.

Common types:

Stream Sockets (TCP) – reliable, used for most applications.

Datagram Sockets (UDP) – used where speed is preferred over reliability.

2. Client-Server Model
Follows a two-part architecture:

Server: Listens for incoming client connections.

Client: Initiates a connection to the server.

Server is passive, waiting for requests; client is active.

3. TCP/IP Protocol
TCP ensures reliable, ordered data transmission.

IP handles addressing and routing between hosts.

4. Basic Socket Functions in Python
socket(): Creates a new socket.

bind(): Binds socket to IP and port.

listen(): Listens for incoming connections.

accept(): Accepts a connection.

connect(): Client uses this to connect to a server.

send() and recv(): Used to send and receive data.

Server-Side Operations:
Create socket → Bind → Listen → Accept connection.

After connection: Use send() and recv() for communication.

Client-Side Operations:
Create socket → Connect to server using IP and port.

After connection: Use send() and recv().

Use Cases of Socket Programming:
Web Servers: Handling HTTP requests.

Chat Applications: Real-time messaging.

File Transfer Protocol (FTP): File transfers.

Online Gaming: Real-time player communication.

Remote Procedure Call (RPC): Code execution on remote systems.

Example Program
Server Code in Python:
python
Copy
Edit
# server.py
import socket
from datetime import datetime

# Create a socket object
s = socket.socket()

# Bind to localhost on port 8000
s.bind(('localhost', 8000))

# Listen for incoming connections
s.listen(5)

# Accept a client connection
c, addr = s.accept()
print("Client Address:", addr)

# Get current date and time
now = datetime.now()

# Send date and time to client
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())

# Receive acknowledgment from client
ack = c.recv(1024).decode()
if ack:
    print(ack)

# Close connection
c.close()
Result:
Thus, the study of Socket Programming using Python was completed successfully, and a server program was implemented to send the current date and time to the client.

