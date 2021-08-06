**Deploy the machine. The attacker has changed the user's password! Can you replicate the attacker's steps and read the flag.txt? The flag is located in the /root/Reptile directory.**
A: N/A

**Run Hydra (or any similar tool) on the FTP service. The attacker might not have chosen a complex password. You might get lucky if you use a common word list.**  

Using the username found during the analysis of the pcap file in the previous task and rockyou.txt password list, bruteforce the server's ftp service using Hydra.
![[_imgs/Pasted image 20210806162419.png]]
Eventually Hydra will provide the new password for the compromised user's account.
![[_imgs/Pasted image 20210806162600.png]]

Answer: *N/A*

**Change the necessary values inside the web shell and upload it to the webserver**  

FTP to the server and login using the credentials obtained from the brute force task.
![[_imgs/Pasted image 20210806162722.png]]
Download the "shell.php" file on the server
![[_imgs/Pasted image 20210806162835.png]]
Open the "shell.php" file and locate the area in the file where the attacker's ip and port is configured.
![[_imgs/Pasted image 20210806162939.png]]
Change the IP and port to your machine's IP and port. Save the changes.
![[_imgs/Pasted image 20210806163023.png]]
Upload the "shell.php" file to the victim's machine.
![[_imgs/Pasted image 20210806163121.png]]

Answer: *N/A*

**Create a listener on the designated port on your attacker machine. Execute the web shell by visiting the .php file on the targeted web server. **

Start a netcat listener on your machine with the port used in the modified "shell.php" file. Navigate to the "shell.php" file on your web browser.
![[_imgs/Pasted image 20210806163257.png]]
![[_imgs/Pasted image 20210806163240.png]]
Using the python3, spawn a TTY shell.
![[_imgs/Pasted image 20210806163604.png]]
Pivot to the compromised user's account using the su command and the password obtained through the brute force attack.
![[_imgs/Pasted image 20210806163907.png]]

Answer: *N/A*

**Become root!** 

Pivot to the root user's account using the sudo su command and the password obtained through the brute force attack.
![[_imgs/Pasted image 20210806174054.png]]

Answer: *N/A*

**Read the flag.txt file inside the Reptile directory**

Now that you are root, read the flag in the "/root/Reptile" directory.
![[_imgs/Pasted image 20210806164231.png]]

Answer: ebce\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
