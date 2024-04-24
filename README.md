# Develop By:INDRAJA.S
# Reg No:21222043003
# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
AIM
ALGORITHM:
Start the program.
Get the frame size from the user
To create the frame based on the user request.
To send frames to server from the client side.
If your frames reach the server it will send ACK signal to client
Stop the Program
PROGRAM
## clinet program:
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

## sever program:
import socket  
s=socket.socket()  
s.connect(('localhost',8000))  
while True:   
print(s.recv(1024).decode())  
s.send("acknowledgement recived from the server".encode())  
## OUPUT
![image](https://github.com/indrajasukumar/2b_SLIDING_WINDOW_PROTOCOL/assets/145115195/fbe50399-1ead-4b27-afd8-472c3192d11c)
![image](https://github.com/indrajasukumar/2b_SLIDING_WINDOW_PROTOCOL/assets/145115195/9a8848ad-0587-4244-8cb7-1b02e34fb8a4)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
