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

![Screenshot 2024-04-12 131940](https://github.com/monishr288/2a_Stop_and_Wait_Protocol/assets/147474049/c15b12f1-2ca9-4459-8421-2abf835698f1)


## SERVER:

![Screenshot 2024-04-12 131951](https://github.com/monishr288/2a_Stop_and_Wait_Protocol/assets/147474049/a77c60f9-87fd-4ed9-af90-74332daaa41b)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
