# Ethicka-Hacking-Techniques---19CS417-
Ethicka Hacking Techniques - 19CS417 
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

SERVER CODE: echo-server.py:

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

CLIENT CODE: echo-client.py:

import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")


## OUTPUT:
SERVER OUTPUT:

![Screenshot 2024-03-05 081809](https://github.com/22008496/Ethicka-Hacking-Techniques---19CS417-/assets/119476113/717ea01f-1441-4a74-b395-2db8943d8811)

CLIENT SIDE:

![Screenshot 2024-03-05 082013](https://github.com/22008496/Ethicka-Hacking-Techniques---19CS417-/assets/119476113/5930af7e-1afa-4632-8729-e808d729b35a)

output:
client:

![264525609-501596a8-0c41-424b-9664-edc5c34acc13](https://github.com/22008496/Ethicka-Hacking-Techniques---19CS417-/assets/119476113/2d1398b1-5f9f-40a5-811a-59b54c5e53b5)


server:


![264525651-52322370-9545-4aeb-af64-a014f1d3febc](https://github.com/22008496/Ethicka-Hacking-Techniques---19CS417-/assets/119476113/42c2b059-2cd0-49d4-94ac-e8391fb22ae6)


## RESULT:
The program is executed successfully
