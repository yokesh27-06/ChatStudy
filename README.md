# Ex.No:1b  			IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: YOKESH H
## REG NO : 212224230312


## Aim: 
To write a python program to perform sliding window protocol
## ALGORITHM:
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:

SERVER

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

CLIENT

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
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

## OUTPUT:

## server.py
<img width="404" height="283" alt="image" src="https://github.com/user-attachments/assets/b21eaab4-2d58-471f-8bd2-bcd3e84f0fba" />



## client.py

<img width="788" height="630" alt="image" src="https://github.com/user-attachments/assets/a821851b-83a9-44e0-a55a-530871ef4b92" />


 
## Result:
Thus the study of Socket Programming Completed Successfully
