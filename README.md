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
## client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,lib=s.accept()
while True:
    i=input("Enter the data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
```      
## server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgemet recieved".encode())

```
## OUTPUT
![image](https://github.com/Vigneshv-23/2a_Stop_and_Wait_Protocol/assets/110780412/e6fd6ad0-b425-4280-b891-bf983b149c0b)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
