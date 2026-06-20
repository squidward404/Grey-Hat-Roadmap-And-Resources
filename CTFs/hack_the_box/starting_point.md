## Note
I recommend having a basic understanding of [Networking](../../Networking/) and [Operating Systems](../../Operating-Systems/) before diving into CTFs. It will make early challenges smoother.
Official Hack The Box site: https://app.hackthebox.com/

## Topic 1 (Starting point)

### 1.1 Meow

Since the questions in this portion are easy and you could quickly look up answers, I will skip the trivial ones and cover the more relevant items.

#### Q. What service do we use to form our VPN connection into HTB labs?
Ans: **OpenVPN**

#### Q. What tool do we use to test our connection to the target with an ICMP echo request?
Ans: **ping**
```bash
ping <target-ip>
```

#### Q. What service do we identify on port **23/tcp** during our scans?
Ans: **telnet**

#### To connect to a server over telnet:
```bash
telnet <target-ip>
```

#### Q. What username is able to log into the target over telnet with a blank password?
Ans: **root** (this is important because it may allow you to log in to a server with a blank password — low-hanging fruit)

Use the above instructions to log in to the server running telnet at the given IP. You already know the default username for a blank password is `root`. After connecting with:

```bash
telnet <target-ip>
```

When prompted for a username, enter `root`. For the password, press Enter. Then run:

```bash
ls
```

You should see the flag file. Open it and submit the flag.

### 1.2 Fawn

#### Q. Which port does the FTP service usually listen on?
Ans: **21**

#### Q. FTP sends data in the clear, without encryption. What acronym is used for the later protocol that provides similar functionality securely as an extension of SSH?
Ans: **SFTP** (Secure File Transfer Protocol)

#### Q. What is the command to display the `ftp` client help menu?
Ans:
```bash
ftp -?
```

#### To connect to an FTP server:
```bash
ftp <target-ip>
```

#### Q. What username is used over FTP to log in without an account?
Ans: **anonymous**

#### Q. What is the response code for the FTP message 'Login successful'?
Ans: **230**

#### Q. What is the command used to download the file we found on the FTP server?
Ans: **get**

Use the above instructions to log in to the FTP server at the given IP. Connect with:

```bash
ftp <target-ip>
```

When prompted for a username, enter `anonymous`. For the password, press Enter. Then run:

```bash
ls
get flag.txt
```

This will download `flag.txt` to your current local directory. Open it and submit the flag.

