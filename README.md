# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## server.py
```
import socket             
s = socket.socket()         
print ("Socket successfully created")
port = 12345                
s.bind(("127.0.0.1",port))         
print ("socket binded to %s" %(port)) 
s.listen(5)     
print ("socket is listening")    
c, addr = s.accept()   
message = c.recv(1024).decode()
fh2=open("sample_copy.txt","w")
fh2.write(message)
print("Client: File Sent")
c.close()
```

## client.py
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client_socket.connect(("127.0.0.1",12345))
print("Connected to server")
fh=open("sample.txt","r")    
data=fh.read()  
client_socket.send(data.encode())
print("Server: Flie Recived")
client_socket.close()
```

## OUTPUT
<img width="958" height="379" alt="image" src="https://github.com/user-attachments/assets/035de8d8-2b16-43ad-8f8f-a7848d76625b" />
<img width="805" height="444" alt="image" src="https://github.com/user-attachments/assets/a6867948-8b1a-4dbe-b124-23ffde1df8dc" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
