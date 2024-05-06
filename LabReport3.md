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
```
@Test 
	public void testReverseInPlace2() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

3.  the output of running the two tests above

![Image](lab4-1.jpg)
We can see that the `testReverseInPlace1()`failed and the `testReverseInPlace2()`passed

4.the before-and-after code change required to fix it 
Before:
```
static void reverseInPlace(int[] arr) {
     for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
     }
}
```
After:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2 ; i += 1) {
      int placeHolder = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = placeHolder;
    }
}
```

5. The original code had servel problem, first, it iterate through the whole list swapping value, this would lead to reversing the array back to its original order. we fix the code by iterating only up to half of the array's length (arr.length/2). the placeHolder variable we added ensures that array elements are correctly swapped without losing their original values.


   ## part2

1. `-i`
\\ example 1
     \\ Command
   
      ```
      grep -i "ISSUE" pmed.0020191.txt
      ```
      Output

      ```
       comments [2] implied that they took a position on this issue.
	```
example2
	Command:
```
christyay@Christys-Air docsearch % grep -i "wHaT" ./technical/plos/pmed.0020191.txt
```
	Output:
 ```
        remains: if such guidelines were to be established, what individuals, institutions,
        permission? Who is to decide what is “historically significant”? Not to mention the
```



  
  
