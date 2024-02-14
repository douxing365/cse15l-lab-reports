## Part 1 - Bugs
1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
- JUnit Test:
  ```
	@Test 
	public void testReverseInPlace() {
    	int[] input1 = { 3, 2, 1 };
    	ArrayExamples.reverseInPlace(input1);
    	assertArrayEquals(new int[]{1, 2, 3 }, input1);
	}
- Associated Code:
  ```
    static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
2.  An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
- JUnit Test:
  ```
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
  
- Associated Code:
  ```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
3.  The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)![Image](symptom.png)
4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
   - before code
     ```
     static void reverseInPlace(int[] arr) {
    	for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
     }
     }
   - after code
     ```
     static void reverseInPlace(int[] arr) {
    	for(int i = 0; i < arr.length / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
   	 }
     }
# Briefly describe why the fix addresses the issue：
The previous code fails because it overwrites elements of the array before swapping them, resulting in the loss of original values. By only iterating through half of the array and using a temporary variable to hold the value of elements during the swap, the issue is resolved, ensuring a correct reversal of the array.<br>

## Part 2 - Researching Commands
1. `-mtime`
   -





