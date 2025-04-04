- [ ] Pasitikrinti ar viskas veikia

**Lab Objective:**

Learn how to migrate to a different process on a target machine after establishing a Meterpreter shell.

**Lab Purpose:**

Meterpreter is a Metasploit attack payload that provides an interactive shell to the attacker from which they can explore the target machine as well as execute code.

**Lab Tool:**

Kali Linux and Windows

**Lab Topology:**

You can use Kali Linux in a VM and a Windows machine for this lab.

**Lab Walkthrough:**

### Task 1:

This lab will continue on from the previous lab, where we use SET to create a payload and establish a Meterpreter shell on a Windows target. In this lab, we will be covering how to migrate to a different process on the Windows machine and some basic privilege escalation.

With your Meterpreter shell open, you should still be connected to yor Windows virtual machine. Type “sysinfo” to gather some information about the target system. In this lab, we will be migrating our Meterpreter shell from its current Meterpreter process to another process on the system. This is a common next step after establishing a shell on a target as it is makes it much easier to avoid detection.

We will begin by typing the following into the Meterpreter console:

ps

This command will list every process running on our Windows machine. Look for the “explorer.exe” process running on the Windows machine. The reason we want to migrate to this process is because it is typically always running on Windows machines. This means that if the user checks their task manager and sees explorer.exe running, they will not be suspicious. However, if they see a process running called “edssddfkj.exe” they may become suspicious, run a malware scan, and we will be caught on the system. Type the following into your meterpreter shell:

ps | grep explorer.exe

This command will list all the processes running on the system and will then use grep to find the explorer.exe process for us. On our machine, it has a Process ID (PID) of 3228.

### Task 2:

We will migrate to this process now by typing the following command:

migrate 3228

![Meterpreter](https://www.101labs.net/wp-content/uploads/2022/04/83-1.png)

We should see something like the following screenshot:

Great, we have successfully migrated to a different process on the Windows system! (2)

![task manager](https://www.101labs.net/wp-content/uploads/2022/04/83-2.png)

### Task 3:

We will now attempt some very basic privilege escalation. Metasploit comes built in with a privilege escalation module. We can load this into Meterpreter by typing the following:

use priv

This will load the privilege escalation module. Once the module is loaded, type the following to attempt privilege escalation on the system (2):

getsystem

This is unlikely to work, but should be tried in any case. If this process fails, your shell may die. If it does, simply run the listener again and execute the payload on the target machine to re-establish the shell.

![Meterpreter](https://www.101labs.net/wp-content/uploads/2022/04/83-3.png)