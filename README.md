# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
## Server.py:
```
import socket

s = socket.socket()

s.bind(('localhost', 5000))

s.listen(5)

print("Waiting for connection...")

c, addr = s.accept()

print("Connected to", addr)

while True:

    ClientMessage = c.recv(1024).decode()

    if not ClientMessage:
        break

    print("Client :", ClientMessage)

    c.send(ClientMessage.encode())

c.close()

s.close()

```

## Client.py:
```
import socket

s = socket.socket()

s.connect(('localhost', 5000))

while True:

    msg = input("Client > ")

    if msg == "exit":
        break

    s.send(msg.encode())

    print("Server >", s.recv(1024).decode())

s.close()

```
## OUTPUT:
## Server:

<img width="1855" height="522" alt="server" src="https://github.com/user-attachments/assets/34b7f8e6-cdd7-4c56-9707-7e74d0022be8" />


## Client:

<img width="1918" height="528" alt="client" src="https://github.com/user-attachments/assets/05042c6b-687b-463c-b28f-632ece214ac3" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
