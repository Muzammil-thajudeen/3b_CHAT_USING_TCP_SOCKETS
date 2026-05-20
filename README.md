# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
##SERVER
```

import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Server Waiting...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    if not ClientMessage or ClientMessage.lower() == "exit":
        print("Connection Closed")
        break

    print("Client >", ClientMessage)

    msg = input("Server > ")
    c.send(msg.encode())

    if msg.lower() == "exit":
        print("Server Stopped")
        break

c.close()
s.close()
```
##cllient
```

import socket

s = socket.socket()
s.connect(('localhost', 8000))

print("Connected to Server")

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    if msg.lower() == "exit":
        print("Connection Closed")
        break

    reply = s.recv(1024).decode()
    print("Server >", reply)

s.close()
```

## OUPUT
<img width="1539" height="1061" alt="image" src="https://github.com/user-attachments/assets/81bc5222-a390-49e5-aa1b-5c1dd60c40c0" />
<img width="1537" height="1062" alt="Screenshot 2026-05-20 153446" src="https://github.com/user-attachments/assets/a8a0f651-8c88-40e4-9d18-20373ef6d9de" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
