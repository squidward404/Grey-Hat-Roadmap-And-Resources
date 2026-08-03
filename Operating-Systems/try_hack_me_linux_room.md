# Linux Fundamentals part 1

> **URL:** https://tryhackme.com/module/linux-fundamentals

---
### Task 1:Introduction 
- Linux is just another operating system like windows and mac which was released in 1991 by Linus Trovalds.

### Task 2:A bit of background on linux
- Linux is well known for being a light weight and open source operating system unlike windows which is proprietary and bloated.
- despite the fact that linux holds less share when it comes to desktops than windows and mac,it runs most servers and smaller computing devices like cell phones.
- Linux has many flavours called distros.

### Task 3:Interacting with your first linux machine(in-browser)
- deploy the machine and read the documentation.

### Task 4:Running your first few commands
- The disadvantage of linux being light weight is that it often doesn’t come with GUI s and uses a CLI(terminal)which might come across as less beginner friendly.

### Task 5:Interacting with the file system
- After logging in,it is important to know how to move around.
- We use commands like ```ls```(to list the contents of a directory), ``` cd```(to change directory),``` cat```(to view the contents of a file), ``` pwd```(to print the current working directory).

### Task 6:searching for files
- instead of using ```cd``` and ```ls``` repeatedly,we can use commands like ``` find``` to easily locate files.
- The first case is,we know the name of the file we are looking for but we don’t know where for example,is the name of the file is `passwords.txt`,we run the command ``` find -name passwords.txt``` 
- The second scenario is we don’t know the name of the file so we use what is known as a wildcard `(*)`.For example,we wanted to find every .txt file,we use the command ``` find -name *.txt```.
- To find a specific content inside a file,we use the ```grep “a_text_we_are_looking_for” filename```.For example ```grep “81.143.211.90” access.log ```
- To search recursively with grep,we use the -R switch ```grep -R “PRETTY_NAME ” /etc/```

### Task 7:An introduction to shell operators
- some of the linux shell operators include:

     1.Operator `&` -used to run commands in the background

     2.Operator `&&` -used to make a list of commands. Example: command1 && command2(the second command will run if and only if command 1 runs).

     3.Operator  `>` -sends the output of a command we run to somewhere else.

     4.Operator `>>` -It have the similar function with `>` ,but instead of overwriting the previous content of the file,it appends it.

### Task 8:Conclusion and summery
