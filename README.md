# EX-6 IMPLEMENTATION OF PING COMMAND

# DATE :13.04.2023

# AIM :
### To write the python program for simulating ping command.
# ALGORITHM :
### Step 1: start the program. 
### Step 2: Include necessary package in java. 
### Step 3: To create a process object p to implement the ping command. 
### Step 4: declare one Buffered Reader stream class object. 
### Step 5: Get the details of the server 
### Step 6: print the results. Step 7: Stop the program.
# CLIENT PROGRAM :
```PY
## Developed : Ziyavudeen A
## Reg no : 212221040189
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
# SERVER PROGRAM :
```PY
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
print(s.recv(1024).decode())

```
# OUTPUT :

![o1](https://github.com/Javith-farkhan/EX-6/assets/94296805/dd4f9506-f05b-4b9d-922a-9989b05a0967)

![o2](https://github.com/Javith-farkhan/EX-6/assets/94296805/8e416b27-cb7b-4688-ba6d-d2e5e8bfe53e)

# RESULT:
### Thus, the python program for simulating ping command was successfully executed.



