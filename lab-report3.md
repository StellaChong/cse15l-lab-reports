Part 1 - Bugs
Bug chosen: Bug in `reverseInPlace` method

1. A failure-inducing input for the buggy program, as a JUnit test and any associated code:
JUnit test code:
```
public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
	}
}
```
2. An input that doesn't induce a failure, as a JUnit test and any associated code:
  ```
public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input2 = { 3 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{ 3 }, input2);
  }
}
```

4. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
  The output shows the ReverseInPlace method did not correctly reverse the given array, for the input {1,2,3} that results failure, it was expected to be 1, but was actually 3.
  ![Image](Result1.png)

5. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
before:
```
   static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
after:
```
 static void reverseInPlace(int[] arr) {
    int temp;
    for(int i = 0; i < arr.length / 2; i++) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
Summary: The fix cut the loop length to only halfway of the array, so that in each loop, it has `temp` to store the front value, and change the after value to the front, and set the after position value to `temp`, which is how the array could be reversed in place. As it won't reset the other half of the array to its original value like it was before fix.

Part 2 - Research
Command chosen: less
Result:
1. `-E`
a. 
```
less -E ./technical/config.ini
setting1=value1
setting2=value2
```
This command attempts to display `config.ini` and exits automatically if the file fits on one screen. It's useful for quickly viewing short configuration files without needing to manually exit.

b. 
```
less -E ./technical/logs/setup.log
[2023-02-26 12:00:00] Setup initiated...
[2023-02-26 12:00:05] Checking prerequisites...
```
Here, less displays setup.log and exits if the log is short enough. It's convenient for scanning brief log files efficiently.

2. `-f`
a. 
```
less -f ./technical/
./
../
config.ini
logs/
scripts/
binaries/
```
Using `-f` to force less to open a directory lists its contents. It can be a quick way to peek into directory structures.

b.
```
less -f ./technical/binaries/app-binary
^@ELF^A^A^A^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^...
```
Opening a binary file with `-f` allows inspection of non-text content, useful for developers examining executables or binary data.

3. `-F`
a.
```
less -F ./technical/scripts/install.sh
#!/bin/bash
```
This command views `install.sh` and exits if it's short, streamlining the process of checking small scripts.

b.
```
less -F ./technical/README.md
This project is...
```
`less -F` opens `README.md`, exiting immediately if the content is brief. It's perfect for quickly checking documentation files.

4. `-N`
a. 
```
less -N ./technical/scripts/deploy.sh
 1  #!/bin/bash
 2  # Deployment script
 ...
```
Viewing `deploy.sh` with `-N` shows line numbers, aiding in referencing specific parts of scripts during reviews or debugging.

b.
```
less -N ./technical/logs/error.log
 1  [2023-02-26 12:05:00] Error: Failed to load configuration
 2  [2023-02-26 12:05:01] Warning: Using default settings
 ...
```
Using `-N` with `error.log` displays line numbers alongside log entries, making it easier to discuss or investigate specific errors.

source: https://phoenixnap.com/kb/less-command-in-linux

