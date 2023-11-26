<h1>SSH Reconnaissance</h1>


<h2>Description</h2>
This project consists of using nmap as a Linux tool to enumerate SSH (port 22) information by using nmap scripts. 
<br />
<br />
<br />

Disclaimer: The Kali Linux user machine and target machine used in this project was provided to me by INE for educational purposes. The misuse of the information in this project lab can result in criminal charges brought against the individual/individuals in question.
<br />


<h2>Languages and Utilities Used</h2>

- <b>nmap</b>


<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Project walk-through:</h2>

<p align="left">
Ping target machine to verify that it is active: <br/>
<br/>
- INE has provided me with Kali Linux GUI & target machine (target machine is one ip address above from mine).  I will run an ip a command to verify my own ip address. Then, I'll run a ping command to verify the target ip address is active.
<br/>
<br/>
Commands: ip a
<br/>
ping -c 5 192.118.151.3
<br/>
<br/>
<img src="https://i.imgur.com/2N4yXWI.png" height="80%" width="80%" alt="SMB Nmap Scripting" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Run nmap scan to look for open tcp ports: <br/>
<br/>
- We can see that the nmap scans found that port 22 (SSH) is open, and it has some version of OpenSSH.
<br/>
<br/>
Commands: nmap 192.118.151.3
<br/>
nmap 192.118.151.3 -p 22 -sV -O
<br/>
<br/>
<img src="https://i.imgur.com/W7fok7a.png" height="80%" width="80%" alt="SMB Nmap Scripting" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Run nmap scan to enumerate how many encryption algorithms are supported by the SSH server: <br/>
<br/>
- We can see that there are 6 encryption algorithms supported by the SSH server.
<br/>
<br/>
Command: nmap 192.118.151.3 -p 22 --script ssh2-enum-algos
<br/>
<br/>
<img src="https://i.imgur.com/U67JMkV.png" height="80%" width="80%" alt="SMB Nmap Scripting" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Run nmap scan to enumerate the ssh-rsa host key that is being used by the SSH server: <br/>
<br/>
Command: nmap 192.118.151.3 -p 22 --script ssh-hostkey --script-args ssh_hostkey=full
<br/>
<br/>
<img src="https://i.imgur.com/r7iKPGO.png" height="80%" width="80%" alt="SMB Nmap Scripting" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Run nmap scan to enumerate which authentication method is being used by the SSH server for users named student & admin: <br/>
<br/>
- It looks like the "student" user authentication method is none_auth, which means there is no authentication method assigned to it.
<br/>
- We can also see that the "admin" user requires a publickey and password.
<br/>
<br/>
Commands: nmap 192.118.151.3 -p 22 --script ssh-auth-methods --script-args="ssh.user=student"
<br/>
nmap 192.118.151.3 -p 22 --script ssh-auth-methods --script-args="ssh.user=admin"
<br/>
<br/>
<img src="https://i.imgur.com/ocHA6pY.png" height="80%" width="80%" alt="SMB Nmap Scripting" class="center"/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />




</p>
