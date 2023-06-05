# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :09.03.2022

AIM :

To write a python program to perform client server model.

ALGORITHM :

Start the program. Get the frame size from the user To create the frame based on the user request. To send frames to server from the client side. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client. Stop the program



PROGRAM :
```
CLIENT:
Developed by : VAISHALI BALAMURUGAN
Register Number : 212222230164
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
 c.close()
```
```
SERVER:
Developed by : VAISHALI BALAMURUGAN
Register Number : 212222230164
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```


OUTPUT:
CLIENT:
![image](https://github.com/VaishaliBalamurugan22008813/19CS406-EX-1/assets/119390134/9e7b1934-cadb-484d-8d7c-23be22485323)

SERVER:
![image](https://github.com/VaishaliBalamurugan22008813/19CS406-EX-1/assets/119390134/0dcb0262-dba1-4bef-86a1-565ce9e8f8f6)

```
RESULT:
 Thus, python program to perform stop and wait protocol was successfully executed.
```
