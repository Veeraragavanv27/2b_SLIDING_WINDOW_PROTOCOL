# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME : VEERARAGAVAN V
## REGISTER NUMBER : 212223230237
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### CLIENT
```py
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr=s. accept()
size=int(input ("Enter number of frames to send"))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
  while(i<len(l)):
   st+=s
   c.send(str(l[i:st]).encode())
   ack=c.recv(1024).decode()
   if ack:
    print(ack)
    i+=s

```
### SERVER
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
## OUTPUT
### CLIENT OUTPUT:
![CLIENT](https://github.com/user-attachments/assets/48fb58a4-9c64-4cea-a9e0-32455160cfc6)


### SERVER OUTPUT:
![image](https://github.com/user-attachments/assets/63b894bd-6192-4c62-888d-ec81d0b7eb83)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
