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
```
b. 
```
less -E ./technical/logs/setup.log
```

2. `-f`
a. 
```
less -f ./technical/
```
b.
```
less -f ./technical/binaries/app-binary
```

3. `-F`
a.
```
less -F ./technical/scripts/install.sh
```
b.
```
less -F ./technical/README.md
```

4. `-N`
a. 
```
less -N ./technical/scripts/deploy.sh
```
b.
```
less -N ./technical/logs/error.log
```

source: https://phoenixnap.com/kb/less-command-in-linux

