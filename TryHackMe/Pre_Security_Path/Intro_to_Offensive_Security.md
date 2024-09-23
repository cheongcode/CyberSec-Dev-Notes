**Task 1**
Offensive security involves breaking into systems, exploiting bugs, and finding vulnerabilities to gain unauthorized access, while defensive security focuses on protecting systems by analyzing and securing against digital threats. Offensive roles simulate a hacker’s actions to find weaknesses and recommend patches, whereas defensive roles investigate hacks, track cybercriminals, and monitor for malicious activity.

Answer the questions below

Which of the following options better represents the process where you simulate a hacker's actions to find vulnerabilities in a system?  

- Offensive Security
- Defensive Security

Answer:
```
Offensive Security
```

**Task 2**
We will use a command-line application called "GoBuster" to brute-force FakeBank's website to find hidden directories and pages. GoBuster will take a list of potential page or directory names and tries accessing a website with each of them; if the page exists, it tells you.

I'm just gonna use TryHackMe's virtual machine for this exercise

![[Pasted image 20240923165128.png]]

We will be running GoBuster for this simple exercise 
```
gobuster -u http://fakebank.com -w wordlist.txt dir
```