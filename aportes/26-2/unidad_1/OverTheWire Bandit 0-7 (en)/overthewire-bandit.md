- Autor: [BLlontopSec](https://github.com/BLlontopSec)
- Fuente original: [overthewire-bandit.md](https://github.com/BLlontopSec/cybersecurity-writeups/blob/main/Cybersecurity/Writeups/Linux%20Fundamentals/overthewire-bandit.md)
- Tipo de documento: **write-up**

---

| Name of the Challenge | OverTheWire - Bandit                                                                                |
| --------------------- | --------------------------------------------------------------------------------------------------- |
| Difficult             | Beginner                                                                                            |
| Description           | Bandit is a wargame designed specifically for beginners in cybersecurity and systems administration |
| Target IP             | -                                                                                                   |

Through a series of practical, challenge-based levels, the game teaches the basics of the Linux command line (CLI). The main objective of each level is to find the hidden password to log in via SSH to the next level, using fundamental commands, tools, and security concepts.

---

> First, I create a directory with the name of our project. In this case, I create a directory called Bandit:

![](./Images/Pasted%20image%2020260920202307.png)


**NOTE:** _In all Bandit levels, the objective of the level will be to find a way to authenticate for the next level, for example by finding the password_

## Level 0 

1. First, we use SSH to connect to **bandit.labs.overthewire.org** on port 2220 and putting the password "bandit0". 

![522](./Images/Pasted%20image%2020260920205010.png)

![228](./Images/Pasted%20image%2020260920205429.png)

**NOTE:** _We are going to do the same for the next levels , when we have the password to authenticate for the next level we are going to go there using SSH_. For example to go to the level 12 we put in the terminal : `ssh bandit12@bandit.labs.overthewire.org -p 2220`

## Level 0 -> 1

1. Create a file to notes and passwords because passwords levels aren't saved automatically (we need to save our passwords here because If we don't save them ourselves, we'll need to start over from bandit0).

![](./Images/Pasted%20image%2020260920210427.png)

2. The password of the next level is in a txt file called "readme" , list the content using the command `ls` and to see the content of the .txt file use the command `cat` 

![569](./Images/Pasted%20image%2020260920214355.png)

## Level 1 -> 2

1. The password of the next level is in a txt file called "-" , But when you try to use the `cat` as a previous level, we realized that it doesn't work.

![](./Images/Pasted%20image%2020260920220011.png)

2. So, if we have a file with the name "-" we must explicitly specify its path. This breaks the command's rule and forces it to search for a file. This happen because "-" is said to act as a placeholder

![318](./Images/Pasted%20image%2020260920220629.png)

## Level 2 -> 3

1. We can't access to the file on the next level because Linux interprets spaces differently; Linux thinks I'm looking for spaces, in, this and filename separately

![475](./Images/Pasted%20image%2020260920222840.png)

2. To solve this problem, it's as simple as putting it in quotation marks and since it starts with a hyphen, we use `./`

![487](./Images/Pasted%20image%2020260920223052.png)

## Level 3 -> 4

1. For the this level we can see that `inhere/` is a directory and we can enter using the command `cd inhere/` and we can see that using `ls` nothing appears and using the command `ls -a` (to also see the hidden content) we can see 2 directories and one file and we can recognized that is a hidden content because all the hidden content in Linux start with a dot 

![302](./Images/Pasted%20image%2020260920224322.png)

2. Since we already know the file name, we use `cat` to read the contents

![461](./Images/Pasted%20image%2020260920224831.png)

## Level 4 -> 5

1. In this level we can access to the password in one file that is "only-human-readable" in the `inhere/` directory.

![](./Images/Pasted%20image%2020260920230201.png)

2. As we can see by reading all the files in the `inhere/` directory, we can observe that the only "human-readable" file is `-file07`. Another way to do it would be using the `file` command, which tells us what type of file the file is (The only ASCII text the can be read by a human is the `-file07`)

![](./Images/Pasted%20image%2020260920231225.png)

## Level 5 -> 6

1. The level said that the password is in a file somewhere under the `inhere/` directory and has the following properties:
	- human-readable
	- 1033 bytes in size
	- not executable

![](./Images/Pasted%20image%2020260920232919.png)

2. As we noticed, it'd be difficult to find the file in many directories since there are several and each directory has its own files. Since the level said that the file have 1033 bytes in size we can use the `find` command , if we can see all the uses of one command we can use `man` before the command, for example : `man find` 

![](./Images/Pasted%20image%2020260920233846.png)

3. We use `find . -size 1033c` the point is to specify that it should search in the current directory the 1033 is the size of the file and c is to specify that is bytes what we put in size. The result showed us where the file is located and if we look closely, this file was a hidden file because it appears with a dot at the beginning, so it'd have been very difficult to do it by opening file by file.

![](./Images/Pasted%20image%2020260920234054.png)

4. Finally, if we go to the location where this file is found, we obtain the password.

![](./Images/Pasted%20image%2020260920234639.png)

## Level 6 -> 7

1. The level said that the password is in a file somewhere on the server and has the following properties:
	- owned by user bandit7
	- owned by group bandit6
	- 33 bytes in size

	As the level said that is somewhere on the server we need to use the `pwd` command to print the currently directory and we can see that we're in `/home/bandit6` to return to see all the server we use the following command `cd ..` every time you want to go back one step

![](./Images/Pasted%20image%2020260921000905.png)

2. Now we are in the server we can use the `find` command to filter according to file properties

![](./Images/Pasted%20image%2020260921001925.png)

3. Since there are files with denied permissions, to hide those files we use the same command followed by `2>/dev/null`. So we have : `find . -size 33c -user bandit7 -group bandit6 2>/dev/null`

![](./Images/Pasted%20image%2020260921001908.png)

4. Finally we do a `cat` command to read the file and we have the password

![](./Images/Pasted%20image%2020260921002136.png)

## Level 7 -> 8

1.  The level said that the password is stored in the file **data.txt** next to the word **millionth** This is very simply with the `grep` command that is used to search for words, phrases or text patterns within files or in the output of other commands. So with `grep "millionth" data.txt"` we have the password for the next level

![](./Images/Pasted%20image%2020260921003233.png)

