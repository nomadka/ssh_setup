Eventhough there are lots of ssh platforms openSSH is the widely used one.

# OpenSSH server setup
Go to start -> Search for 'Optional features -> View features -> Search for OpenSSH server -> select that and proceed to install
Get-Service sshd #Shows the basic information of server
# OpenSSH client setup
ssh username@ip_address #Connects to a server with password
ssh-keygen #Command to generate key pairs with default algorithm (rsa)
man ssh-keygen #Opens the manual with description of differnt configuration or algorithm
ssh-keygen -t rsa -b 4096
ssh-keygen -t dsa 
ssh-keygen -t ecdsa -b 521
ssh-keygen -t ed25519 #Command for various key pair algorithms in openSSH
ssh-copy-id-i ~/.ssh/keyname.pub username@ip_address #If you already have established a password based ssh connection this commands copies your ssh public key into the remote server
# If you dont have established a connection yet copy the public key manually into the server location ~/.ssh/authorized_keys
notepad "C:\ProgramData\ssh\sshd_config" #Open the server configuration file in text editor, and uncomment 'PubkeyAuthentication yes' (Make sure to restart the ssh server if any configuration changes has been done)
ssh username@ip_address #This connects to the server without asking password; if pub key is stored in different location use ssh username@ip_address -i ~/{location}
