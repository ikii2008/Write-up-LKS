# Write-Up: TryHackme, Offensive Security Intro


<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/offensive-security-intro.png" alt="Offensive Security Intro">
</p>

---

## Task 1 Think Like a Hacker!

In task 1, it is explained that this room will take the user through website hacking training, with simulations in a safe and legal environment. The user is then asked which term is used to describe the act of hacking to find vulnerabilities in a system, and the answer is offensive security.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task1.png" alt="task1">
</p>

## Task 2 Starting the Lab

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task2.png" alt="task2">
</p>

In task 2, it is explained that this room uses a virtual desktop for the simulation, and the user will be taken to the virtual system after clicking the view site menu that is available.

Before moving on to the virtual system, there is a description provided for the site, which is `A fake banking app called FakeBank will be launched. When the lab loads, you will see a banking app running in your browser`. In this room, the user has to find `what the bank account number displayed in the FakeBank app is`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task2-site.png" alt="task2-site">
</p>

After the user heads to the available site, they will be taken to the system, which displays a site named `FakeBank`. On this site there is some available information such as the account, account number, and transactions. In line with the question given, which is what account number is displayed on FakeBank, the account number displayed is `8881`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task2-complete.png" alt="task2-complete">
</p>

## Task 3 Find Hidden Pages
---

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3.png" alt="task3">
</p>

In task 3, the user will look for weaknesses in the FakeBank website.

It is explained that:

After clicking the "View Site" button above, the user will start using the terminal. The terminal is used to interact with devices and cybersecurity tools.

One common mistake websites make is leaving hidden pages accessible. We will use the terminal to run a command that can search for these.

In the terminal, copy and paste the dirb command below and wait until it finishes. Every line of the output that starts with + is a page that has been found.

```bash
dirb http://fakebank.thm
````

`Dirb` will find two URLs. Use this information to answer the questions below.

In this task, the user will use the `dirb` tool.

`Dirb` is a tool used for brute forcing so the user can find hidden directories and files on a website server.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3-terminal.png" alt="task3-terminal">
</p>

On the provided site, the user is directly given a terminal to run the dirb tool. In line with the available description, we will use the command `dirb http://fakebank.thm`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3-dirbuster.png" alt="task3-dirbuster">
</p>

The scan is complete, and `dirb` has found two directories, which are `/bank-transfer` and `/images`. It was already known that there is an `images` directory on the website server and we are asked what the other hidden directory is, so we answer task 3 with `http://fakebank.thm/bank-transfer`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3-complete.png" alt="task3-complete">
</p>

## Task 4 Attack the Admin Page
---

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4.png" alt="task4">
</p>

In task 4, the user is required to find a hidden admin panel that allows the user to add money to their account. In this task, it is explained that we have to head to the `admin` panel. In task 3, we found a directory, which is `bank-transfer`, and in this task 4 the user is also required to use that directory to dig up the information needed. So here we will use a `URL path exploit` technique in the form of `directory traversal`.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-site.png" alt="task4-site">
</p>

The provided site will take us to the `FakeBank` website. In line with the instructions, we have to add `/bank-transfer` to the URL.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-bank-transfer.png" alt="task4-bank-transfer">
</p>

On this page, we are required to enter the account number `8881` and an amount of money of `$2000` or more.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-flag.png" alt="task4-flag">
</p>

After clicking deposit, a flag appears, which means we have gotten the answer for this task 4.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-complete.png" alt="task4-complete">
</p>

```
FLAG: BANK-HACKED
```

## Conclusion
---

In this room, we are taught several website hacking techniques and theories, such as the use of `dirb` and the `directory traversal` technique, where these tools and techniques are related to each other and are one of the weaknesses that an attacker can use to exploit a website.
