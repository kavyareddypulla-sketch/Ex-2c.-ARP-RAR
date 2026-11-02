## AIM:   
To write a python program for simulating ARP/RARP protocols using TCP. 

## ALGORITHM: 
## Client:
Start the program
Using socket connection is established between client and server.
Get the IP address to be converted into MAC address.
Send this IP address to server.
Server returns the MAC address to client.
## Server:
Start the program
Accept the socket which is created by the client.
Server maintains the table in which IP and corresponding MAC addresses are stored.
Read the IP address which is send by the client.
Map the IP address with its MAC address and return the MAC address to client. P

## PROGRAM - ARP

## SERVER
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

print("Connected to ARP Client")

while True:
    ip = input("Enter logical Address: ")

    s.send(ip.encode())

    mac = s.recv(1024).decode()
    print("MAC Address:", mac)
```
## CLIENT 
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

print("Connected to ARP Client")

while True:
    ip = input("Enter logical Address: ")

    s.send(ip.encode())

    mac = s.recv(1024).decode()
    print("MAC Address:", mac)
```

## OUPUT - ARP
## SERVER

<img width="857" height="253" alt="image" src="https://github.com/user-attachments/assets/8426ef3b-f295-4261-8103-bd2a07904c36" />

## CLIENT 

<img width="697" height="128" alt="image" src="https://github.com/user-attachments/assets/d9885c2e-f333-4fb4-9324-c470912c4ebf" />

## PROGRAM - RARP
## SERVER
```
import socket

s = socket.socket()
s.connect(('localhost', 9000))

print("Connected to RARP Client")

while True:
    mac = input("Enter MAC Address: ")

    s.send(mac.encode())

    ip = s.recv(1024).decode()
    print("Logical Address:", ip)
```


## OUPUT -RARP
##SERVER
<img width="782" height="270" alt="image" src="https://github.com/user-attachments/assets/ed537a58-b455-4deb-8d7c-a95d47bb1cc0" />

## CLIENT
<img width="782" height="167" alt="image" src="https://github.com/user-attachments/assets/8a34f06e-99b2-4f7b-abad-503257db9e1b" />

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully executed.
