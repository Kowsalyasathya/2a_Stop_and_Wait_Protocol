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
## PROGRAM:
### Client:
```
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
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
### Client:
![307229758-30dc1d63-faa9-4937-806f-8a3a52082dcb](https://github.com/Kowsalyasathya/2a_Stop_and_Wait_Protocol/assets/118671457/9e7d6ae1-e10f-4957-b6d7-a8e0c52fff45)
### Server:
![307229804-ae19718a-f4ae-47aa-8451-fc0e143657c0](https://github.com/Kowsalyasathya/2a_Stop_and_Wait_Protocol/assets/118671457/da5df664-3f82-439c-8fcd-930b9684b4ea)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
