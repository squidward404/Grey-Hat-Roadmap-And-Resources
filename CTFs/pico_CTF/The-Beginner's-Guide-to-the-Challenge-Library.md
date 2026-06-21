## Note
I recommend having a basic idea of [Networking](../../Networking/) and [Operating Systems](../../Operating-Systems/) before you dive into CTFs. It will make the early challenges feel much smoother.
Official picoCTF site: https://picoctf.org

## Section 1 (Sanity)

### 1.1 Obedient Cat

When you start a CTF, always check the hints. They are often the fastest way to learn what the challenge is teaching.

#### Hint 1
"Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal."

What this means:
- Anything after `$` is a command you should type in the terminal.

#### Hint 2
"To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget and a link to the flag. The link can be copied from the details section."

What to do:
1. Copy the link to the file from the challenge details (right click -> copy link address).
2. Run the command below, replacing the URL with the link you copied:

```bash
wget <link-to-the-flag>
```

For this challenge, the link is:
```
https://challenge-files.picoctf.net/c_wily_courier/94960d0ab62213382ae31be6ee984974308794c01d681308f5094b9ff30270d6/flag
```

This downloads a file named `flag` into your current folder. Use `ls` to confirm it is there.

#### Hint 3
"$ man cat"

What to do:
- `cat` prints a file to the screen. You can read the downloaded file with:

```bash
cat flag
```

The output is the flag. Submit it, and you are done.

### 1.2 Super SSH
Secure Shell (SSH) is going to be pretty important. Can you SSH as `ctf-player` to `titan.picoctf.net` on port `58449` to get the flag? You will need the password `1ad5be0d`. If prompted, accept the fingerprint with `yes`.

#### Hint 1
https://linux.die.net/man/1/ssh
- This link takes you to an SSH manual to read and understand what SSH is all about.

#### Hint 2
You can try logging in "as" someone with <user>@titan.picoctf.net
What to do:
- Use the command below to connect as the `ctf-player` user:

```bash
ssh ctf-player@titan.picoctf.net
```

#### Hint 3
How could you specify the port?
What to do:
- Add the `-p` flag for the port:

```bash
ssh ctf-player@titan.picoctf.net -p 58449
```

#### Hint 4
Remember, passwords are hidden when typed into the shell
What to do:
- Passwords do not appear while you type. Enter the SSH password `1ad5be0d` and press Enter.

After entering the password and connecting successfully, you will see the message `Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_8306c99d}`. Submit the flag and you are done.

### 1.3. What's a net cat?
Using netcat (`nc`) is going to be pretty important. Can you connect to `fickle-tempest.picoctf.net` at port `58116` to get the flag?

#### Hint 1
nc tutorial
What to do:
- Look up how to connect with `nc`, then run:

```bash
nc fickle-tempest.picoctf.net 58116
```
After running the command, you will see the message `You're on your way to becoming the net cat master picoCTF{nEtCat_Mast3ry_95035DAa}`. Submit the flag and you are done.

## Section 2 (Cyber Chef)

### 2.1 MOD 26
Cryptography can be easy. Do you know what ROT13 is?

Download the text file `values.txt`.

#### Hint 1
This can be solved online if you don't want to do it by hand!
What to do:
- Use an online decoder to decrypt the text. You can use https://cryptii.com/

Take a look at the downloaded file by running `cat values.txt` in the downloaded directory. The output is `cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_45559noq}`, which is encrypted using ROT13. Decrypt it using Cryptii, then submit the flag. Done.

### 2.2 Warmed Up
Instance:What is 0x3D (base 16) in decimal (base 10)?

#### Hint 1
Submit your answer in our flag format. For example, if your answer was '22', you would submit 'picoCTF{22}' as the flag.

The decimal equivalent of the hexadecimal number 3D is 61
Submit the flag as `picoCTF{61}`. Done.

### 2.3 2warm
Instance:Can you convert the number 42 (base 10) to binary (base 2)?

#### Hint 1
Submit your answer in our competition's flag format. For example, if your answer was '11111', you would submit 'picoCTF{11111}' as the flag.

The same thing as the previous challenge. The binary equivalent of 42 is 101010, so the flag becomes `picoCTF{101010}`.

### 2.4 Bases
Instance:What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

#### Hint 1
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

The question is what type of encoding is used for bDNhcm5fdGgzX3IwcDM1. It is Base64. When decoded using Cryptii, it becomes l3arn_th3_r0p35. Submit it in the format `picoCTF{l3arn_th3_r0p35}`.


## Section 3

### 3.1 Wave a flag
Instance: Can you invoke help flags for a tool or binary? This program includes a helpful "help" message.

When you follow the challenge link it downloads an executable named `warm`. Run the following commands in the directory where you downloaded it:

```bash
chmod +x warm
./warm
# The program will print something like:
# Hello user! Pass me a -h to learn what I can do!
./warm -h
# The help output includes the flag; submit it.
```

What to do:
- Make the file executable: `chmod +x warm`
- Run the program: `./warm`
- Run it with the `-h` flag to show the help message and flag: `./warm -h`

### 3.2 Tab, Tab Attack
After unzipping, this problem can be solved using Tab completion.

A zip file named `Addadshashanammu.zip` is provided. Download and unzip it, then change into the extracted directory:

```bash
unzip Addadshashanammu.zip
cd Addadshashanammu
ls
```

You should see a file or nested directories (for example `Almurbalarammi`). The hint suggests using `cd` and Tab completion (press Tab repeatedly) to reveal hidden or nested names and navigate to the flag.

What to do:
- Unzip the archive and use `cd` with Tab completion to discover the flag location.

### 3.3 Insp3ctOr
Instance: Inspect the web page source to find three parts of the flag.

How to inspect:
- In the browser, right-click and choose "Inspect" (or press Ctrl+Shift+C) to open Developer Tools.
- Check the HTML, CSS, and JavaScript panels for hidden comments.

What you'll find:
- In the HTML (an HTML comment): <!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 --> (first part)
- In the CSS (a comment): /* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
- In the JavaScript (a comment): /* JavaScript sure is neat. Anyways part 3/3 of the flag: _lucky?302945a7} */

Putting those together yields the full flag:

```
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?302945a7}
```

What to do:
- Inspect the page source (HTML/CSS/JS) and combine the three parts to form the complete flag.

