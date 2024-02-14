## Part 1 Bugs
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
4.  The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
5. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
