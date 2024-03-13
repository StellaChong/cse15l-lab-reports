Lab Report 5
Part1- Debugging Scenario

1. Original Post by a Student:
Title: Trouble with Unexpected Output in Java Program Using Bash Script
Content
Hi,
I'm working on a Java program that's supposed to read a list of numbers from a file, calculate their sum, and print the result. I've written a Bash script to compile and run my program, passing the file name as an argument. While the output I'm getting is not what I expected, it's just printing the first number from the file.
I've attached a screenshot of the terminal output after running my script. Could it be that I'm not reading the file correctly in Java, or is my Bash script not passing the file name properly?
Screenshot:
Terminal showing the output of running the Bash script, which only prints the first number from the input file.
![]()

2. TA response:
It's interesting that it's only printing the first number. Maybe you can try running your Bash script with bash -x to see the commands being executed and share the output? This might give us more insight into whether the issue is with how the script is passing the file name or something within your Java code.

3. Follow-up from student(with fixed code):

4. Setting
File and directory structure:
SumNumbers.java - Java file that reads numbers from a file and prints their sum.
runSum.sh - Bash script to compile and run SumNumbers.java.

Contents before fixing:

Command line:

Description of possible edits:


Part2- Reflection
