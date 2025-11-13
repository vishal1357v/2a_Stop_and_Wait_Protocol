# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Server
```python

import socket 
s=socket.socket() 
s.connect(('localhost',7000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

## Client
```python

import socket 
s=socket.socket()
s.bind(('localhost',7000))
s.listen(5) 
c,addr=s.accept() 
while True: 
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close() 
        break
```
## OUTPUT
<img width="1920" height="1200" alt="Screenshot 2025-10-13 133803" src="https://github.com/user-attachments/assets/3bd17935-f2ac-421a-b502-988ac20f7030" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
