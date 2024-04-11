# 2a_Stop_and_Wait_Protocol
## Name:MONISH R
## Reg no:212223220061
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
# CLIENT:
```python
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
## SERVER
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())  
```
## OUTPUT
## CLIENT:

![image](https://github.com/AshwinKumar-Saveetha/2a_Stop_and_Wait_Protocol/assets/155129814/c974d6eb-c9d4-4fe9-8658-0ae9a83429aa)

## SERVER:

![image](https://github.com/AshwinKumar-Saveetha/2a_Stop_and_Wait_Protocol/assets/155129814/9fac3e9f-7f5d-4c94-9a8d-836d4c453af5)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
