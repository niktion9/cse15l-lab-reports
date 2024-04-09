# Lab Report 1
## Examples of the cd Command
> ### Example 1 (cd command with no arguments):

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ cd
Nikithas-MacBook-Pro:~ nikitha$ pwd
/Users/nikitha
```

Working Directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Output Explanation: The cd command stands for "change directory", meaning it takes a directory as an argument and allows the user to move from the current directory to the one mentioned. Since there was no argument following the cd command, the working directory was changed from ```lecture1``` to the default ```nikitha``` directory (absolute path: ```/Users/nikitha```). I used to the ```pwd``` command to attain the information on the working directory.

Error or No Error: It is not an error.

> ### Example 2 (cd command with directory argument):

```
Nikithas-MacBook-Pro:~ nikitha$ pwd
/Users/nikitha
Nikithas-MacBook-Pro:~ nikitha$ cd lecture1/
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ 
```

Working Directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha```

Explantion: In the filesystem, the directory present is ```lecture1```, which is home to a few files and the ```messages``` directory (which contain messages of "hello world" in different languages). This time, ```lecture1/``` is mentioned as the argument for the cd command, which changed the working directory to ```lecture1``` (absolute path: ```/Users/nikitha/lecture1```). I used to the ```pwd``` command to attain the information on the working directory.

Error or No Error: It is not an error.

> ### Example 3 (cd command with file argument):

```
Nikithas-MacBook-Pro:lecture1 nikitha$ cd messages/
Nikithas-MacBook-Pro:messages nikitha$ pwd
/Users/nikitha/lecture1/messages
Nikithas-MacBook-Pro:messages nikitha$ cd fi.txt
bash: cd: fi.txt: Not a directory
Nikithas-MacBook-Pro:messages nikitha$ 
```
Working Directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1/messages```

Explanation: For this example, I have decided to use the languages files existing in the ```messages``` directory as the file parameter. So I first made sure that I am in the correct directory, for which I ran the command ```cd messages/```. The output of entering a the ```fi.txt``` file (the Finnish "hello file" I created during lab) as a parameter was an error message that indicated that ```fi.txt``` is not a directory. 

Error or No Error: This trial resulted into an error because the cd command only changes directories, and ```fi.txt``` is a file.


## Examples of the ls Command
> ### Example 1: ls command with no arguments

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ ls
Hello.class     Hello.java      README          messages
Nikithas-MacBook-Pro:lecture1 nikitha$ 
```

Working directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Explanation: The ls command is responsible for listing the files and folders in a given path. Since the working directory, according to the ```pwd``` command, was ```/Users/nikitha/lecture1```, the output of having no arguments to the ls command is a mention of all the content, that is files and directories (```Hello.class     Hello.java      README       messages```) in ```lecture1```.

Error or No Error: It is not an error.

> ### Example 2: ls command with directory argument

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ ls messages
en-us.txt       es-mx.txt       fi.txt          zh-cn.txt
Nikithas-MacBook-Pro:lecture1 nikitha$ 
```

Working directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Explanation: Since ```messages``` was a directory within the working directory ```lecture1```, I used it as a parameter for this example. With the ```ls messages``` command,  the output was the list of the language files consisted within the ```messages``` directory (```en-us.txt       es-mx.txt       fi.txt          zh-cn.txt```).

Error or No Error: It is not an error.

> ### Example 3: ls command with file argument

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ ls Hello.java
Hello.java
```

Working directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Explanation: Since the absolute path of the working directory is still ```/Users/nikitha/lecture1```, I decided to used ```Hello.java``` as the file argument, as it resides with ```lecture1```. Once the command was run, as predicted the code in ```Hello.java``` file was excuted successfully, and the expected result of ```Hello.java``` was printed. the code in ```Hello.java``` ensures that the first arguments after the command gets printed. In this case, it was just the filename ```Hello.java```.

Error or No Error: It is not an error.


## Examples of the cat command
> ### Example 1: cat command with no arguments

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ cat
hi
hi
hello there
hello there
```

Working directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Explanation: A ```cat``` command, short for "concatenate", is responsible for printing the details of one or more files mentioned as arguments. However, run without any arguments, the cat command does not return any details, but outputs a completely blank line in which it expects an input (the inputs in this case were ```hi``` and ```hello there```) and returns what was entered.

Error or No Error: It is not an error.

> ### Example 2: cat command with directory argument

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ cat messages
cat: messages: Is a directory
Nikithas-MacBook-Pro:lecture1 nikitha$
```

Working directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Explanation: Since the only directory within ```lecture1``` was ```messages```, it was used as an argument, which outputted a statement indicating that ```messages``` is a directory, rather than a file. The cat command only prints the details present in a mentioned file, not a directory.

Error or No Error: Yes, it is an error because the cat command does not accept a directory as an argument. It will only work with files.

> ### Example 3: cat command with file argument

```
Nikithas-MacBook-Pro:lecture1 nikitha$ pwd
/Users/nikitha/lecture1
Nikithas-MacBook-Pro:lecture1 nikitha$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
Nikithas-MacBook-Pro:lecture1 nikitha$ cat Hello.java README
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}To use this program:

javac Hello.java
java Hello messages/en-us.txt
Nikithas-MacBook-Pro:lecture1 nikitha$ 

```

Working Directory: Right before the command was run, the absolute path of the working directory was ```/Users/nikitha/lecture1```

Explanation: Since the cat command has the ability to print details of *one or more* files, I have tried two approaches for this example. I first put in one file argument, which was ```Hello.java```. Just as expected, the code in ```Hello.java``` was displayed. Then, I tried the cat command with two files, one being ```Hello.java``` and the other being the ```README``` file. As expected, the output was a combination of the content present in both the files.

Error or No Error: It is not an error.



