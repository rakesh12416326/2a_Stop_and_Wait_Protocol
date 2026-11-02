# 2a_Stop_and_Wait_Protocol
## DATE:24/10/2026
## AIM:
To write a python program to perform stop and wait protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### SERVER PROGRAM:
```
import socket

s = socket.socket()
s.bind(("localhost", 8000))
s.listen(1)

print("Server waiting for client...")

c, addr = s.accept()
print("Client connected!")

while True:
    data = c.recv(1024).decode()

    if data == "exit":
        break

    print("Data received:", data)

    c.send("ACK".encode())
    print("Acknowledgement sent")

c.close()
s.close()
```
### CLIENT PROGRAM:
```

import socket

s = socket.socket()
s.connect(("localhost", 8000))

n = int(input("Enter number of messages: "))

for i in range(n):
    data = input("Enter data to send: ")

    s.send(data.encode())

    ack = s.recv(1024).decode()
    print("Acknowledgement received:", ack)

s.send("exit".encode())
s.close()

```
## OUTPUT
<img width="1912" height="1013" alt="Screenshot 2026-11-02 133936" src="https://github.com/user-attachments/assets/76dfb330-4fcb-4497-a67b-473cc7691b74" />
<img width="1912" height="1002" alt="Screenshot 2026-11-02 134003" src="https://github.com/user-attachments/assets/cda88075-846d-464c-8e89-2596a5df7c64" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
