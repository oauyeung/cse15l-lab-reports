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
```
2.An input that doesn't induce a failure

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

### 1. `-i`
   
example 1

Command:
   
      ```
      cd technical/plos
      grep -i "ISSUE" pmed.0020191.txt
      ```
Output:

      ```
       comments [2] implied that they took a position on this issue.
	```
 This commend `-i` gets the string from the file provided but it ignore case sensitivity, without this command-line options the output would of been empty because there is no string "ISSUE" in the file, but due to this command-line options it also looked for string with all lower case "issue". Also, I first cd into the correct directory with the file located.

example2

Command:
```
grep -i "wHaT" ./technical/plos/pmed.0020191.txt
```
Output:
 ```
        remains: if such guidelines were to be established, what individuals, institutions,
        permission? Who is to decide what is “historically significant”? Not to mention the
```
 This command-line option `-i` gets the string from the directory provided into the file but it ignore case sensitivity, without this command-line options the output would of been empty because there is no string "whaT" in the file, but due to this command-line options it also looked for string with all lower case "what".

### 2. `-c`

example1

command:

```
cd technical/plos
grep -c "issue" pmed.0020191.txt
```

Output:

```
1
```

example2

command:

```
grep -i "what" ./technical/plos/pmed.0020191.txt
```

Output:

```
2
```

The command-line option -c counts the lines number when the strings in the file provided, in example 1 there is 1 line with "issue" so it outputted 1, in the example 2 I used a directory of a file as augument but it did the same thing and count thw line with "what"


### 3. `-v`

example1

command:

```
cd technical/plos
grep -v "issue" pmed.0020191.txt
```

Output:

```
        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
        Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against
        biohistorical research; instead, it points out that such investigations are currently
        taking place without guidelines—ethical, scientific, moral, or religious. The question
        remains: if such guidelines were to be established, what individuals, institutions,
        governments, medical examiners, family members, or intrepid biographers are to be given
        permission? Who is to decide what is “historically significant”? Not to mention the
        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
```

example2

command:

```
grep -v "what" ./technical/plos/pmed.0020191.txt
```

Output:

```
        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
        Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against
        biohistorical research; instead, it points out that such investigations are currently
        taking place without guidelines—ethical, scientific, moral, or religious. The question
        governments, medical examiners, family members, or intrepid biographers are to be given
        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
        comments [2] implied that they took a position on this issue.
```

The command-line option -v prints the line that does not include the string provided, As we can see it didn't print any line with the key word provided.

### 4.`-n`

example1

command:

```
cd technical/plos
grep -n "what" pmed.0020191.txt  
```

Output:

```
10:        remains: if such guidelines were to be established, what individuals, institutions,
12:        permission? Who is to decide what is “historically significant”? Not to mention the
```
The command-line option -n prints the line that include the string provided and also provide the line number that String showed up before the line, as we can see from the output the string "what" showed up on line 10 and 12 of the file.


example2

command:

```
grep -vn "what" ./technical/plos/pmed.0020191.txt
```

Output:

```
1:
2:  
3:    
4:      
5:        
6:        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
7:        Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against
8:        biohistorical research; instead, it points out that such investigations are currently
9:        taking place without guidelines—ethical, scientific, moral, or religious. The question
11:        governments, medical examiners, family members, or intrepid biographers are to be given
13:        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
14:        comments [2] implied that they took a position on this issue.
15:      
16:    
17:  
```

I combined the use of two command line option v and n. The command-line option -vn prints the line that does not include the string provided and provide the line number of those lines, As we can see, the numbering skipped 10 and 12 as those line include the keyword "what". And it also prints and number all empty lines as it also doesn't include "what".



  
  
