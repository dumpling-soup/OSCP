
# Journey to OSCP
## Background
No formal training in red-team or OCO. This is just a hobby. At the time of writing this, the certs I have are:
* CompTIA Security+
* GIAC Certified Intrusion Analyst (GCIA)
* eLearnSecurity Junior Penetration Tester (eJPT)
* eLearnSecurity Certified Professional Penetration Tester (eCPPTv2)
* Offensive Security Certified Professional (OSCP)
## Why
Just because... 

## Exam Format
**Exam.** The exam is 5 stand-alone boxes that are unrelated to one another. You are given 23 hours and 45 minutes to work on the exam and another 24 hours after that to write and submit a report on your findings.

There are 4 "traditional" boxes that require initial access and sometimes privilege escalation. 1 is worth 10 points, 2 are worth 20 points, and the last one is worth 25 points. 

Lastly, there is a "buffer overflow" box. A separate (ungraded) development box is provided with a sample of a vulnerable server and a client script. Students are expected to analyze the vulnerable application locally and develop a buffer overflow exploit that will result in a shell to the "buffer overflow" box. This box is worth 25 points. 

All boxes add up to 100 points and you need 70 points to pass. Full points are granted for achieving root access. Though some people suspect that low-privilege access is half point, Offensive-Security does not publicly disclose how many points a low-privilege access is worth.

The exam is proctored via webcam and screen sharing. You have to notify the proctor whenever you leave to take a break or go to sleep (yes, you are expected to sleep and eat like a normal person).

Also, Metasploit and automated tools like SQLmap or Nessus are not allowed not the exam. 

## Exam Experience
*1300 Friday (0/100)*
I started with the buffer overflow box, as this is the simplest in my opinion. Once you understand the process, the steps are the same every time. While I completed the required steps in 45 minutes, it took me well around 2 hours to achieve root on this box. Check your commands very carefully... I forgot "quotes" in my command and could not figure out why MSFvenom wouldn't generate my exploit correctly and cost me over an hour.

*1500 Friday (25/100)*
While I was working on that, I had my enumeration scripts running in the background. By the time I was done with the buffer overflow box, they had been done. I attempted to crack the 25 point box by carefully reading the outputs of my scans. Anyone who has taken OSCP will tell you that rabbit holes are dangerous and can be detrimental to your exam results. Sadly, I was a victim. I spent way too long on this box without making any progress.

*1830 Friday (25/100)*
I took a break for dinner and to stretch out a little bit. I made absolutely no progress for the following few hours...

*2030 Friday (25/100)*
I knew I had fallen in a rabbit hole, swallowed my pride, and moved onto the a 20 point box. Enumeration, service selection, and exploits were on point and I achieved initial access with ease. A quick look at the system information was enough to let me know what privilege escalation method to try. Succeeded and achieved root on this box.

*2300 Friday (45/100)*
I took a crack at the other 20 point box. Like before, enumeration was good and I did not have too much difficulty locating the vulnerability, getting initial low-privilege access. There was no obvious exploit to throw at this one to gain privilege escalation. I uploaded a script that checks for misconfigurations and other common privilege escalation possibilities. After combing through the results, I found the misconfiguration and exploited that to gain root. 

*0145 Saturday (65/100)*
At this point, was thinking two things. 
1. Had I done the practice lab reports for the course, I would get an extra 5 points and have enough to pass.
2. I had to get either an initial access into the 25 point box or root the 10 point box.

I began to look at the 10 point box. Though it's only worth 10 points, I've often heard people say don't underestimate it. They couldn't have been more right. There's not much I can say without leaking the exam, so just remember that you have plenty of reverts on the boxes. Throw whatever exploit you find and if you break the box, just revert it.

*0330 Saturday (75/100)*
I finally had enough points to pass. I gathered the screenshots I needed for my report and notified the proctor that I was going to sleep for a few hours.

*0700 Saturday (75/100)*
I woke up, rushed through my normal morning routine, and went back at the 25 point box. Made some progress but not enough to achieve initial access.

*1130 Saturday (75/100)*
At this point, I had given up on the 25 point box. While it would have been nice to say I got a 100 on OSCP, it wasn't necessary for the certification. I grab some nicer screenshots of my previous exploitations (reverted some boxes to do so) and began organizing them for my report. My exam ended at 1245.

**Report.** 
I used a standard template report from Offensive-Security. Nothing fancy. Just made sure I read over the exam requirements carefully and included all the information/screenshots that were required of the report.

**Final Remarks.** 
* Don't go down a rabbit hole.
* Eat. Sleep. Take breaks.
* Allocate your time accordingly.
* There are plenty of reverts. Sometimes, Hail Mary attempts work... just throw some exploit at it if you are absolutely in a bind.

## Recommended Tools
I didn't use a whole lot of fancy tools that weren't shipped with Kali.

**Autorecon.** https://github.com/Tib3rius/AutoRecon

**LinEnum.** https://github.com/rebootuser/LinEnum

## Recommended Training
I had a weird mix of different training I did for this. I've organized it into a better "path" for folks trying this out.

**Starting in Pen-Testing** 
* TryHackMe: Complete Beginner
	* https://tryhackme.com/path/outline/beginner
* TryHackMe: Offensive Pentesting
	* https://tryhackme.com/path/outline/pentesting
* eLearnSecurity (eJPT)/PTS training by INE (free)
	* https://elearnsecurity.com/product/ejpt-certification/
	* Course is free and does a very good job at going through the pen-test methodology. Exam is 3 day pen-test with multiple choice questions about it.

**Preparing for OSCP**
* eLearnSecurity (eCPPTv2)/PTP training by INE
	* https://elearnsecurity.com/product/ecpptv2-certification/
	* This exam is a 7 day black-box pen test. Class is very informative and exam is fun (requires pivoting, which is not tested on OSCP). 7 more days to write the report.
* HackTheBox (Search for TjNull's recommended boxes)
* PWK Lab (Comes with OSCP exam attempt)
* Offensive Security Proving Grounds

**Priv Esc Training (Absolutely Essential)**
* Linux Privilege Escalation for Beginners
	* https://www.udemy.com/course/linux-privilege-escalation-for-beginners/
* Windows Privilege Escalation for Beginners
	* https://www.udemy.com/course/windows-privilege-escalation-for-beginners/

## Things I Wish I Studied More
**Web App Pen Test.** I struggled a lot at this and wished I studied/practiced much more than I had. Being comfortable with manual SQL injections and proxying requests through Burp Suite will go a long way.

## What's Next?
**OSCE3.** Next 3 Offensive-Security courses/exams.
* OSEP - Experienced Penetration Tester
* OSWE - Web Expert
* OSED - Exploit Developer

**Active Directory.** HackTheBox and PentesterAcademy has great content on red teaming a network with active directory.
