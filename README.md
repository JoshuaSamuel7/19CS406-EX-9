# EX-9 APPLICATION USING TCP SOCKETS - CREATING FOR CHAT CLIENT-SERVER

## DATE : 03/05/2023

## AIM :
To write a python program for creating Chat using TCP Sockets Links.

## ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user.
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server, it will send ACK signal to client otherwise it
will sendNACK signal to client.
6. Stop the program
```

## PROGRAM :
## CLIENT :
```PYTHON 3
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 msg=input("Client > ")
 s.send(msg.encode())
 print("Server > ",s.recv(1024).decode())
```

## SERVER :
```PYTHON 3
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 ClientMessage=c.recv(1024).decode()
 print("Client > ",ClientMessage)
 msg=input("Server > ")
 c.send(msg.encode())
```

## OUTPUT :
## CLIENT :

![9A](https://github.com/JoshuaSamuel7/19CS406-EX-9/assets/118343296/ffc121e3-be07-4af5-9ebb-1e6978e4e293)

## SERVER :

![9B](https://github.com/JoshuaSamuel7/19CS406-EX-9/assets/118343296/f83ba898-e21d-4e32-879d-859d827b0264)

## RESULT :
Thus, the python program for creating Chat using TCP Sockets Links was successfully
created and executed.
