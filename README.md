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
## server.py:
```
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

```
## client.py:

```
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
## server.py:

<img width="651" height="237" alt="Screenshot 2026-10-26 205310" src="https://github.com/user-attachments/assets/9e5bf9a2-0819-482c-be71-22ee6de4b214" />


## client.py:
<img width="786" height="166" alt="Screenshot 2026-10-26 205327" src="https://github.com/user-attachments/assets/11e914ea-1206-4d32-85ee-49068040f513" />



## RESULT:
The program is executed successfully
