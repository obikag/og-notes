URL: https://tryhackme.com/room/h4cked

**Download the .pcap file and use Wireshark to view it.**  
Answer: N/A

**The attacker is trying to log into a specific service. What service is this? **

Download and open "Capture.pcapng" file
![[Pasted image 20210806154112.png]]
Look at any one of the early packets and you will observe that the attacker is attempting to connect to port 21, which is linked to the FTP service.
![[Pasted image 20210806154248.png]]

Answer: *ftp*

**There is a very popular tool by Van Hauser which can be used to brute force a series of services. What is the name of this tool?  **

Doing a simple Google search for "Van Hauser security tool" provides us with the tool name.

Answer: *Hydra*

**The attacker is trying to log on with a specific username. What is the username?  **

Scrolling through the packet captures, you will notice a TCP request that containts a username.
![[Pasted image 20210806154845.png]]
Right click on the packet and select Follow -> TCP Stream
![[Pasted image 20210806155104.png]]
In the "Follow TCP Stream" window you will find the username being used in the bruteforce attack.
![[Pasted image 20210806155131.png]]

Answer: *jenny*

** What is the user's password?  **

Continue scrolling through the packet captures. Eventually you will observe a TCP request that containts a password followed by an "Login successful" response.
![[Pasted image 20210806155349.png]]
Right click on the packet and select Follow -> TCP Stream
![[Pasted image 20210806155424.png]]
In the "Follow TCP Stream" window you will find the password.
![[Pasted image 20210806155546.png]]

Answer: *password123*

**What is the current FTP working directory after the attacker logged in?  **

In the same "Follow TCP Stream" window, you will find the working directory.
![[Pasted image 20210806155644.png]]

Answer: */var/www/html*

**The attacker uploaded a backdoor. What is the backdoor's filename?  **

In the same "Follow TCP Stream" window, you will find the backdoor that was uploaded.
![[Pasted image 20210806155742.png]]

Answer: *shell.php*

**The backdoor can be downloaded from a specific URL, as it is located inside the uploaded file. What is the full URL?**  

Continue scrolling through the packet captures. Eventually you will observe a FTP-DATA transfer request that containts the backdoor data with the description (STOR shell.php). 
![[Pasted image 20210806160024.png]]
Right click on the packet and select Follow -> TCP Stream
![[Pasted image 20210806160217.png]]
In the "Follow TCP Stream" window you will find the web url.
![[Pasted image 20210806160105.png]]

Answer: http://pentestmonkey.net/tools/php-reverse-shell

**Which command did the attacker manually execute after getting a reverse shell?**  

Scroll through the packets and search for a GET request for the "shell.php" file. After the get request, look for a connection from the attacker's port 80 to the victim machine.
![[Pasted image 20210806160519.png]]
Right click on the packet and select Follow -> TCP Stream
![[Pasted image 20210806160557.png]]
In the same "Follow TCP Stream" window you will find the command.
![[Pasted image 20210806160638.png]]

Answer: *whoami*

**What is the computer's hostname?**

In the same "Follow TCP Stream" window that was used to find the previous command, scroll down to find the hostname after the attacker spawned a TTY shell.
![[Pasted image 20210806160730.png]]

Answer: *wir3*

**Which command did the attacker execute to spawn a new TTY shell?**

In the same "Follow TCP Stream" window that was used to find the previous command, scroll down to find the TTY spawn shell command.
![[Pasted image 20210806160824.png]]

Answer: *python3 -c 'import pty; pty.spawn("/bin/bash")'*

**Which command was executed to gain a root shell?**  

In the same "Follow TCP Stream" window that was used to find the previous command, scroll down to find the super user command.
![[Pasted image 20210806161344.png]]

Answer: *sudo su*

**The attacker downloaded something from GitHub. What is the name of the GitHub project?**  

In the same "Follow TCP Stream" window that was used to find the previous command, scroll down to find GitHub url.
![[Pasted image 20210806161419.png]]
Following the GitHub url provides us with the project for the backdoor.
![[Pasted image 20210806161456.png]]

Answer: *Reptile*

**The project can be used to install a stealthy backdoor on the system. It can be very hard to detect. What is this type of backdoor called?**

The features of Reptile indicates that its a rootkit.
![[Pasted image 20210806161556.png]]

Answer: *rootkit*
