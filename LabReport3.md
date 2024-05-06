# Lab Report 3
## Part1- Bug
The code I picked is `reverseInPlace(int[] arr)` method in the file`ArrayTest.java`
1. failure-inducing input
```
@Test 
	public void testReverseInPlace1() {
    int[] input1 = {1,2,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,2,1}, input1);
}

2.An input that doesn't induce a failure
```
@Test 
	public void testReverseInPlace2() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


3.  the output of running the two tests above
4.  
