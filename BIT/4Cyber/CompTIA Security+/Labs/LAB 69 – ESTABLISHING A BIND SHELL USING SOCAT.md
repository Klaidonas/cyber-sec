**Lab Objective:**

Learn how to use the socat tool to get a bind shell on a target.

**Lab Purpose:**

Socat is a command line-based utility that establishes two bi-directional byte streams and transfers data between them. Socat can be used for many different purposes due to its versatility.

**Lab Tool:**

Kali Linux and Metasploitable VM.

**Lab Topology:**

You can use Kali Linux in a VM for this lab.

**Lab Walkthrough:**

### Task 1:

In this lab, we will be using socat to create a bind shell on a metasploitable machine. If you are unfamiliar with metasploitable, it is an intentionally vulnerable machine which can be loaded in VMware, the same as Kali Linux. You can download the metasploitable iso file here: [https://docs.rapid7.com/metasploit/metasploitable-2/](https://docs.rapid7.com/metasploit/metasploitable-2/)

You can find a lot of material on this page on how to download and setup the Metasploitable VM.

![Metasploitable VM](attachements/Metasploitable_VM-1.png)

We will use both Kali Linux and Metasploitable for this lab. Remember to put both machines on the same isolated host-only network to talk to each other. When login is required, you will enter “**msfadmin**” as username and password.

### Task 2:

Socat comes pre-installed on Kali Linux. The main difference between netcat and socat is that the syntax for using socat is more difficult to understand. Socat is used to make connections between two points. These points can be anything. We will begin by creating a bind shell connecting our Kali VM to our Metasploitable VM.

First, let’s find out the eth0 IP address of our Metasploitable VM and write it down. We will use this information on our Kali VM. Open a terminal screen in Metasploitable VM and type this command:

ifconfig

![Metasploitable VM](attachements/Metasploitable_VM-3.png)

192.168.56.102 is IP address of our Metasploitable VM in this case.

Then, establish a listener on our Metasploitable VM by typing the following:

socat TCP-L:8080 EXEC:”bash -li”

This creates a listener on our Metasploitable VM and is the equivalent to typing “nc -lvnp 8080” in netcat.

### Task 3:

We will then switch to our Kali VM and type the following to connect to our Metasploitable VM:

socat TCP:192.168.56.102:8080 –

If we return to our Kali terminal and attempt to execute commands such as “id” and “whoami”, we can see that we have successfully established a shell to our Metasploitable VM.

![socat](attachements/socat-1.png)

This is an unstable bind shell and it is non-interactive, as you can see processes such as SSH do not work. Ctrl + c will also kill the shell. This is a useful technique to know, however, in the event that netcat does not work. Socat is also very versatile and it is much easier to stabilise the shell, as you will see in a later lab.

If we were to attempt to establish a bind shell using socat on a windows machine, we would need to change the syntax of the listener on our Windows machine. The syntax for our listener on a Windows machine would change to the following:

socat TCP-L:8080 EXEC:powershell.exe,pipes

This command will use the Windows Powershell instead of bash to create the shell. The pipes option forces powershell to use Unix style standard input and output, which makes it easier for us to use the shell.