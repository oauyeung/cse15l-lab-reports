# Lab Report 3
## Part1- Bug
The code I picked is `reverseInPlace(int[] arr)` method in the file`ArrayTest.java`

```
{
@Test 
	public void testReverseInPlace() {
    int[] input1 = {1,2,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,2,1}, input1);
	}
}
