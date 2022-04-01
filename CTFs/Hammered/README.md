<h1 align="center"> Hammered CTF Walkthrough </h1>

<h3 align="center">

![](Images/Hammered_Completed.png)

</h3>

<p>
This challenge takes you into the world of virtual systems and confusing log data. In this challenge, figure out what happened to this webserver honeypot using the logs from a possibly compromised server.

The following skills that are gained/utilized in this challenge are: `Log Analysis` `WebServer` `Honeypot` `Apache2`
</p>
<br></br>

<h1> First Impressions </h1>
<p>
Before we take any further actions on the challenges or do any investigations, we need to realize the initial scope of the CTF. Looking at the challenge instructions, we are given a zip file and a list of files to focus our analysis on:

    File Name: c26-Hammered.zip
    File Size: 944 KB
    SHA1SUM: c5282824e485cbafe4b13a942759fd6720433929

Make sure you verify the **SHA1SUM** hash value of any files you download by doing the following (this will verify the integrity of the downloaded file):

![](Images/Sha1sum_check.png)

Below are all files that are present after extracting the zip archive:

![](Images/Hammered_Extracted.png)

**Files in Scope**:
- kern.log
- auth.log
- daemon.log
- dmesg
- apache2


</p>
<br></br>

<h1> Challenge Questions </h1>

### Q1. Which service did the attackers use to gain access to the system?
<p>

First we can check and verify what log file is needed for this problem which can be found in [this article](https://www.eurovps.com/blog/important-linux-log-files-you-must-be-monitoring/). You can conclude that the `auth.log` file is of interest, so we can look with this command:

```bash
grep "fail" auth.log | less
```

```log
pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=8.12.45.242  user=root
pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=8.12.45.242  user=root
pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=8.12.45.242  user=root
pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=8.12.45.242  user=root
```         

From this output we can see that there are many attempts to login via `sshd`.

**Answer** ✅: SSH
</p>
<br></br>

### Q2. What is the operating system version of the targeted system?
<p>
For this question you can actually find the awnser to this 2 deferent ways:

You look into the `kern.log` file, as it contains information logged by the kernel. Try this:

```bash
head kern.log
```

```
kernel: Inspecting /boot/System.map-2.6.24-26-server
kernel: Loaded 28787 symbols from /boot/System.map-2.6.24-26-server.
kernel: Symbols match kernel version 2.6.24.
kernel: Loaded 14773 symbols from 62 modules.
kernel: [    0.000000] Initializing cgroup subsys cpuset
kernel: [    0.000000] Initializing cgroup subsys cpu
kernel: [    0.000000] Linux version 2.6.24-26-server (buildd@crested) (gcc version 4.2.4 (Ubuntu 4.2.4-1ubuntu3)) #1 SMP Tue Dec 1 18:26:43 UTC 2009 (Ubuntu 2.6.24-26.64-server)
```

You also look into the `dmesg` file, as it contains information contains Kernel ring buffer messages, device status, hardware errors and other generic messages. Try this:

```bash
head dmesg
```
```
[    0.000000] Initializing cgroup subsys cpuset
[    0.000000] Initializing cgroup subsys cpu
[    0.000000] Linux version 2.6.24-26-server (buildd@crested) (gcc version 4.2.4 (Ubuntu 4.2.4-1ubuntu3)) #1 SMP Tue Dec 1 18:26:43 UTC 2009 (Ubuntu 2.6.24-26.64-server)
[    0.000000] Command line: root=UUID=a691743a-a4b7-482d-95ff-406e5acd83a3 ro quiet splash
[    0.000000] BIOS-provided physical RAM map:
[    0.000000]  BIOS-e820: 0000000000000000 - 000000000009f800 (usable)
[    0.000000]  BIOS-e820: 000000000009f800 - 00000000000a0000 (reserved)
[    0.000000]  BIOS-e820: 00000000000ca000 - 00000000000cc000 (reserved)
[    0.000000]  BIOS-e820: 00000000000dc000 - 00000000000e4000 (reserved)
[    0.000000]  BIOS-e820: 00000000000e8000 - 0000000000100000 (reserved)
```

**Answer** ✅: 4.2.4-1ubuntu3
</p>
<br></br>

### Q3. What is the name of the compromised account?

From our previous investigation in the first question, we can see that most of the attempts were done via the `root` user account.

**Answer** ✅: root

</p>
<br></br>

### Q4. Consider that each unique IP represents a different attacker. How many attackers were able to get access to the system?
<p>

</p>
<br></br>

### Q5. Which attacker's IP address successfully logged into the system the most number of times?
<p>

</p>
<br></br>

### Q6. How many requests were sent to the Apache Server?
<br></br>

### Q7. How many rules have been added to the firewall?
<p>

</p>
<br></br>

### Q8. One of the downloaded files to the target system is a scanning tool. Provide the tool name.
<p>

</p>
<br></br>

### Q9. When was the last login from the attacker with IP 219.150.161.20? Format: MM/DD/YYYY HH:MM:SS AM
<p>

</p>
<br></br>

### Q10. The database displayed two warning messages, provide the most important and dangerous one.
<p>

</p>
<br></br>

### Q11. Multiple accounts were created on the target system. Which one was created on Apr 26 04:43:15?
<p>

</p>
<br></br>

### Q12. Few attackers were using a proxy to run their scans. What is the corresponding user-agent used by this proxy?
<p>

</p>
<br></br>