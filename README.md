# 2a_Stop_and_Wait_Protocol
## AIM
## DATE:24/10/2026
To write a python program to perform stop and wait protocol
## ALGORITHM
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
## OUTPUT
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
