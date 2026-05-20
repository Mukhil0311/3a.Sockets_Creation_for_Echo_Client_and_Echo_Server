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

SERVER SIDE:

```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server waiting for connection...")
c, addr = s.accept()
print("Connected to:", addr)
while True:
   
    client_message = c.recv(1024).decode()

  
    if not client_message:
        break

    print("Client:", client_message)

   
    c.send(client_message.encode())


c.close()
s.close()
```

CLIENT SIDE:

```
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = "localhost"
port = 8000

client.connect((host, port))

print("Connected to server...")

while True:
    message = input("Enter Message : ")

    if message == "quit":
        break

    client.sendall(message.encode())

    reply = client.recv(1024).decode()

    print("Received from Server :", reply)

client.close()
```
## OUPUT

SERVER OUTPUT

![image](https://github.com/Mukhil0311/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/blob/main/Screenshot%202026-05-20%20102022.png)

CLIENT OUTPUT

![image](https://github.com/Mukhil0311/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/blob/main/Screenshot%202026-05-20%20102034.png)


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
