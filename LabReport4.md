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
<img alt = "step1Lab3.png" src = "https://github.com/niktion9/cse15l-lab-reports/blob/main/step1Lab3.png?raw=true">

Working Directory: before and after running cd without parametrs: ```/home``` during the call of cd: ```/lecture1```

Output Explanation: The cd command stands for "change directory", meaning it takes a directory as an argument and allows the user to move from the current directory to the one mentioned. Since there was no argument following the cd command, the working directory was changed from ```/lecture1``` to the default ```/home``` directory.

Error or No Error: It is not an error.
