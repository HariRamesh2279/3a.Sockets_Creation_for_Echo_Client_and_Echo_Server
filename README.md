# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM:
```python
echo_server.py

import socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1' 
port = 5000 
server_socket.bind((host, port)) 
server_socket.listen(1) 
print("Echo Server is waiting for connection...") 
client_socket, addr = server_socket.accept()
print("Connected to:", addr) 
while True: 
    data = client_socket.recv(1024).decode() 
    if not data: 
        break 
    print("Client:", data) 
    client_socket.send(data.encode()) 
# Close sockets 
client_socket.close() 
server_socket.close() 

echo_client.py

import socket 
# Create socket object 
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
# Connect to server 
host = '127.0.0.1' 
port = 5000 
client_socket.connect((host, port)) 
while True: 
    # Input message 
    message = input("Enter message: ") 
    # Send message to server 
    client_socket.send(message.encode()) 
    if message.lower() == 'exit': 
        break 
    # Receive echoed message 
    data = client_socket.recv(1024).decode() 
    print("Server echoed:", data) 
# Close socket 
client_socket.close() 
```
## OUPUT:

server.py

<img width="752" height="447" alt="Screenshot 2026-11-18 104820" src="https://github.com/user-attachments/assets/a233c306-8333-4a60-8d0a-4881e6e1de71" />

client.py

<img width="857" height="440" alt="Screenshot 2026-11-18 104931" src="https://github.com/user-attachments/assets/193141f8-9c30-4fee-a6ea-c58c762ffd88" />



## RESULT:

Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
