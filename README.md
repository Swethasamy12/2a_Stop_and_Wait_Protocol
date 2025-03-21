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
CLIENT:
```
import socket
from datetime import datetime
 
s=socket.socket()
 
s.bind(('localhost',8000))
 
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
 
now = datetime.now()
 
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
 
if ack:
    print(ack)
 
c.close()

```
SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
print(s.getsockname()) 
print(s.recv(1024).decode()) 
s.send("acknowledgement recived from the server".encode()) 

```
## OUTPUT
CLIENT:

![Screenshot 2025-03-20 142757](https://github.com/user-attachments/assets/5f27e947-8a21-4000-973f-fc93e9aa5ff1)


SERVER:

![Screenshot 2025-03-20 143316](https://github.com/user-attachments/assets/d02c81a5-7a7b-4784-9a6a-3bd4f22052d6)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
