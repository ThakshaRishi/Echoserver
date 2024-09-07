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

## Client:
```
import socket

HOST = "127.0.0.1" 
PORT = 65432 

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")
```

## Server:
```
import socket


HOST = "127.0.0.1"  
PORT = 65432 

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
```

## OUTPUT:

## Client:

![Screenshot 2024-09-07 172445](https://github.com/user-attachments/assets/919bbb35-40e1-45f4-95b7-dbddc660e6c1)

## Server:

![Screenshot 2024-09-07 172501](https://github.com/user-attachments/assets/a9fb9e19-0922-4901-b817-a0d7c8602be5)


## RESULT:
The program is executed successfully
