For each of the commands cd, ls, and cat, and using the workspace you created in this lab:
1. Share an example of using the command with no arguments.
2. Share an example of using the command with a path to a directory as an argument.
3. Share an example of using the command with a path to a file as an argument.

For commands `cd`: <br />
Using the command with no argument: <br />
Command: `cd` <br />
Working directory: `/home` <br />
Output: No output to this command, as it changes the directory to the user's home directory <br />
Explanation: Running `cd` without arguments will default to changing the working directory to the user's home directory. There is no error here. <br />
![Image](cd1.png)

Using the command with a path to a directory as an argument: <br />
Command: `cd lecture1` <br />
Working Directory: `/home/lecture1` <br />
Output: No visible output <br />
Explanation: This command will change the working directory from `/home` to `/home/lecture1`, there should be no error as `lecture1` exists <br />
![Image](cd2.png)

Using the command with a path to a file as an argument: <br />
Command: `cd Hello.java` <br />
Working Directory: `/home/lecture1` <br />
Output: `bash: cd: Hello.java: Not a directory` <br />
ExplanationL This command fails as `Hello.java` is a file, not a directory. While `cd` needs a directory as its argument, the error will occur. <br />
![Image](cd3.png)

For commands `ls`: <br />
Using the command with no argument: <br />
Command: `ls` <br />
Working directory: `/home/lecture1` <br />
Output: `Hello.class  Hello.java  messages  README` <br />
Explanation:`ls` will list the contents of the `lecture1` directory, showing `Hello.java`,`README`, and the `messages` directory <br />
![Image](ls1.png)

Using the command with a path to a directory as an argument: <br />
Command: `ls messages` <br />
Working directory: `/home/lecture1` <br />
Output:`en-us.txt  es-mx.txt  zh-cn.txt` <br />
Explanation: The command will list contents of the directory `messages` inside `lecture1`, showing the text files inside as shown in the output. <br />
![Image](ls2.png)

Using the command with a path to a file as an argument: <br />
Command: `ls Hello.java` <br />
Working directory: `/home/lecture1` <br />
Output: `Hello.java` <br />
Explanation: The command will confirm the existence of `Hello.java` file in the `lecture1` directory. <br />
![Image](ls3.png)

For commands `cat`: <br />
Using the command with no argument: <br />
Command: `cat` <br />
Working directory: `/home/lecture1` <br />
Output: No output <br />
Explanation: As `cat` will read the user input to write standard output, as there's no input here, there won't be an output here. <br />
![Image](cat1.png)

Using the command with a path to a directory as an argument: <br />
Command: `cat messages` <br />
Working directory: `/home/lecture1` <br />
Output:`cat: messages: Is a directory` <br />
Explanation: It causes an error because `cat` expects a file path, not a directory. <br />
![Image](cat2.png)

Using the command with a path to a file as an argument: <br />
Command:`cat Hello.java` <br />
Working directory: `/home/lecture1` <br />
Output: <br />
~~~
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharset
s.UTF_8);    
    System.out.println(content);
  }
  ~~~
Explanation: The command will display the content of code `Hello.java`, as `Hello.java` exists as a file in the `lecture1` directory. <br />
![Image](cat3.png)
