## Note
I recommend having a basic idea of Networking and Operating Systems before you dive into CTFs. It will make the early challenges feel much smoother.
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

