# Lab Report 1
## Examples of the cd Command
> ### Example 1 (cd command with no arguments):

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ 
```

Working Directory: before and after running cd without parametrs: ```/home``` during the call of cd: ```/lecture1```

Output Explanation: The cd command stands for "change directory", meaning it takes a directory as an argument and allows the user to move from the current directory to the one mentioned. Since there was no argument following the cd command, the working directory was changed from ```/lecture1``` to the default ```/home``` directory.

Error or No Error: It is not an error.

> ### Example 2 (cd command with directory argument):

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```

Below is a codeblock, where I used the pwd (print working directory) command to check what the working directory was after the running the cd command with a directory as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$
```

Working Directory: ```/lecture1``` directory

Explantion: In the filesystem, the only directory present is lecture1, which is home to a few files and the messages directory (it contains messages of "hello world" in different languages). This time, lecture1 is mentioned as the argument for the cd command, which resulted in a new terminal line with the context "~/lecture1" before the dollar sign, indicating that we are sucessfully transitioned into the lecture1 directory, causing no errors.

Error or No Error: It is not an error.

> ### Example 3 (cd command with file argument):

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd testCd
bash: cd: testCd: Not a directory
[user@sahara ~]
```
Working Directory: ```/home``` directory

Explanation: For this example, I have added a new file in the filesystem outside of the lecture1 directory, call testCd. The output for entering a testCd as a parameter was an error message that indicated that testCd is not a directory. 

Error or No Error: This trial resulted into an error because the cd command only changes directories, and testCd is a file.


## Examples of the ls Command
> ### Example 1: ls command with no arguments

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls
lecture1  testCd
[user@sahara ~]$ 
```

Working directory: ```/home``` directory

Explanation: The ls command is responsible for listing the files and folders in a given path. Since the working directory/path was the home directory, the output of having no arguments to the ls command is a mention of lecture1 folder/directory and the testCd file, in other words, the contents of the home directory.

Error or No Error: It is not an error.

> ### Example 2: ls command with directory argument

```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$
```

Working directory: ```/lecture1``` directory

Explanation: With the lecture1/ directory as the specified argument, the ls command listed the files and folder that lecture1 consisted of in the filesystem.

Error or No Error: It is not an error.

> ### Example 3: ls command with file argument

```
[user@sahara ~]$ ls testCd
testCd
[user@sahara ~]$ ls lecture1/README
lecture1/README
[user@sahara ~]$
```

Working directory: ```/home``` directory (approach 1) and ```/lecture1``` directory (approach 2)

Explanation: I have tried two appraoches with having a file as an argument. I first tried the single testCd file which has no additional content to it, and the output for that is just the file name. I have also used the README file in the lecture1 directory as a parameter and the command once again, since the argument is a file, it just listed its name, lecture1/README.

Error or No Error: It is not an error.


## Examples of the cat command
> ### Example 1: cat command with no arguments

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cat
hi
hi
helloo
helloo

```

Working directory: ```/home``` directory

Explanation: A cat command, short for "concatenate", is responsible for printing the details of one or more files mentioned as arguments. However, run without any arguments, the cat command does not return any details, but outputs a completely blank line in which it expects an input (the inputs in this case we "hi" and "helloo") and returns what was entered.

Error or No Error: It is not an error.

> ### Example 2: cat command with directory argument

```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$
```

Working directory: ```/lecture1``` directory

Explanation: Since the only directory in the filesystem is lecture1, it was used as an argument, which outputted a statement indicating that lecture1 is a directory, rather than a file. The cat command only prints the details present in a mentioned file.

Error or No Error: Yes, it is an error because the cat command does not accept a directory as an argument. It will only work with files.

> ### Example 3: cat command with file argument

```
[user@sahara ~]$ cat testCd
Hi!!
This file outside lecture1 used for test file arguments!
[user@sahara ~]$ cat testCd lecture1/README
Hi!!
This file outside lecture1 used for test file arguments!
To use this program:

javac Hello.java
java Hello messages/en-us.txt
[user@sahara ~]$
```

Working Directory: ```/home``` directory (for approach 1) and ```/lecture1``` directory (for approach 2)

Explanation: Since the cat command has the ability to print details of *one or more* files, I have tried two approaches for this example. I have put some text is the testCd file and used that as my first argument, which resulted in the message that was in the file. Then, I also tried the cat command with two files, one being testCd and the other being the README file in lecture1. As expected, the output was a combination of the content present in both the files.

Error or No Error: It is not an error.



