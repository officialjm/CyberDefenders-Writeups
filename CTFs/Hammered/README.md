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

Make sure you verify the **SHA1SUM** hash value of any files you download by doing the following:

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

</p>
<br></br>

### Q2. What is the operating system version of the targeted system?
<br></br>

### Q3. What is the name of the compromised account?
<br></br>

### Q4. Consider that each unique IP represents a different attacker. How many attackers were able to get access to the system?
<br></br>

### Q5. Which attacker's IP address successfully logged into the system the most number of times?
<br></br>

### Q6. How many requests were sent to the Apache Server?
<br></br>

### Q7. How many rules have been added to the firewall?
<br></br>

### Q8. One of the downloaded files to the target system is a scanning tool. Provide the tool name.
<br></br>

### Q9. When was the last login from the attacker with IP 219.150.161.20? Format: MM/DD/YYYY HH:MM:SS AM
<br></br>

### Q10. The database displayed two warning messages, provide the most important and dangerous one.
<br></br>

### Q11. Multiple accounts were created on the target system. Which one was created on Apr 26 04:43:15?
<br></br>

### Q12. Few attackers were using a proxy to run their scans. What is the corresponding user-agent used by this proxy?
<br></br>