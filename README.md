# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
```
SERVER.py:

import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
 
 
 CLIENT.py
 
 import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## OUTPUT:
![Screenshot (17)](https://github.com/user-attachments/assets/3675d29c-44fc-4446-b77b-5cb47370ff11)
![Screenshot 2024-09-13 200732](https://github.com/user-attachments/assets/ea98d2bd-7d8c-40fb-85da-be18bf203c65)
![Screenshot 2024-09-13 200752](https://github.com/user-attachments/assets/211226c1-8ed8-48a6-a514-7fd7cc1114af)




## RESULT:
The program is executed successfully
