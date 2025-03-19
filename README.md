# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME : Shehan Shajahan
## REGISTRATION NO. : 212223240154
## AIM :
Implementation Of Sliding Window Protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM :
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter Window Size: "))
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
## SERVER :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recieved from the server".encode())
```
## OUPUT :
![Screenshot 2025-03-19 103636](https://github.com/user-attachments/assets/e514bf7a-eeb3-4478-8a19-91940ed2e8f9)
![Screenshot 2025-03-19 103719](https://github.com/user-attachments/assets/f203ddf6-5503-46ca-9a8d-ba76f6603fc9)

## RESULT :
Thus, python program to perform stop and wait protocol was successfully executed
