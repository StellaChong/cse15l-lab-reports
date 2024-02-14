Part 1 - Bugs
Bug chosen: Bug in `reverseInPlace` method

1. A failure-inducing input for the buggy program, as a JUnit test and any associated code:
JUnit test code:
```
public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3,4 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 4,3,2,1 }, input1);
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


Part 2 - Research


