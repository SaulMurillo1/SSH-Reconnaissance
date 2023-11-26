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




</p>
