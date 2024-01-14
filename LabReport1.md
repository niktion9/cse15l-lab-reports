# Lab Report 1
## Examples of the cd Command
> ### Example 1 (cd command with no arguments):

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd
[user@sahara ~]$
```

Here is a codeblock, where I used the pwd (print working directory) command to check what the working directory was after the running the cd command with no arguments:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd
[user@sahara ~]$ pwd
/home
```

Working Directory: home directory (/home)

Explanation: The cd command stands for "change directory", meaning it takes a directory as an argument and allows the user to move from the current directory to the one mentioned. Since there was no argument following the cd command, the working directory is still the home directory, thus outputting just a new empty command line.

> ### Example 2 (cd command with directory argument):

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```

Here is a codeblock, where I used the pwd (print working directory) command to check what the working directory was after the running the cd command with a directory as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$
```

Working Directory: lecture1 directory

Explantion: In the filesystem, the only directory present is lecture1, which is home to a few files and the messages directory (its contain messages of "hello world" in different languages). This time, lecture1 is mentioned as the argument for the cd command, which resulted in a new terminal line with the context "~/lecture1" before the dollar sign, indicating that we are sucessfully transitioned into the lecture1 directory, causing no errors.

> ### Example 3 (cd command with file argument):

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd testCd
bash: cd: testCd: Not a directory
[user@sahara ~]
```
Working Directory: home directory (/home)

Explanation: For this example, I have added a new file outside of the lecture1 directory to the filesystem, call testCd. The output for enetring a testCd as a parameter was an error message that testCd is not a directory. This trial resulted into an error because the cd command only changes directories, not files.

## Examples of the ls Command
> ### Example 1: ls command with no arguments

