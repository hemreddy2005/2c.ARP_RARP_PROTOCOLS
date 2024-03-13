# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
```
 

import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```
## OUPUT - ARP
![312133340-1fd438f8-e57e-45af-9a70-03c98cdfaf9b](https://github.com/hemreddy2005/2c.ARP_RARP_PROTOCOLS/assets/145633111/fca346c5-4ff2-43ce-a5a1-71dae1b2dfea)

## PROGRAM - RARP
``` 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 

    ip=input("Enter logical Address : ") 
    s.send(ip.encode()) 
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![312133394-2050f737-7f8f-4b9d-965b-1a24493f928f](https://github.com/hemreddy2005/2c.ARP_RARP_PROTOCOLS/assets/145633111/fef2210b-eeb5-47eb-9056-8e3d158aab90)
## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
