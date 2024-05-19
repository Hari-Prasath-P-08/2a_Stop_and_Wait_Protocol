# 2a_Stop_and_Wait_Protocol

### Name: HARI PRASATH. P
### Reg. No: 212223230070

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

### Server:

```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT:

![322830242-ee9220a1-63e8-407f-8afb-eccba52aba9e](https://github.com/Hari-Prasath-P-08/2a_Stop_and_Wait_Protocol/assets/139455593/94f0bbc8-bbc0-46d0-8d6a-85ce79f19a9c)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
