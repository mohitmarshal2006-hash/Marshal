import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_ip = "127.0.0.1" 
server_port = 12345
client_socket.connect((server_ip, server_port))
print("Connected to server)
message = "Hello Server!"
client_socket.send(message.encode())
response = client_socket.recv(1024)
print("Server says:", response.decode())
client_socket.close()
