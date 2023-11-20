# Lab Report 3
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Part 1
**Bug Chosen:** `reversed` method in `ArrayExamples`

**Failure Inducing Input:**
 ```
 @Test
  public void testReversedFailure() {
    int[] input1 = {8,7,6,5};
    assertArrayEquals(new int[]{5,6,7,8}, ArrayExamples.reversed(input1));
  }
```

**Non-failure Inducing Input:**
```
@Test
 public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
 }
```

**Symptoms**
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/628c7ab5-e7b3-4f8c-9e4c-2eb01e9088e1)

**The Buggy Code Before:**
```
   static int[] reversed(int[] arr) {
       int[] newArray = new int[arr.length];
       for(int i = 0; i < arr.length; i += 1) {
         arr[i] = newArray[arr.length - i - 1];
       }
       return arr;
     }
```
**The Buggy Code After (Fixed):**
```
   static int[] reversed(int[] arr) {
       int[] newArray = new int[arr.length];
       for(int i = 0; i < arr.length; i += 1) {
         newArray[i] = arr[arr.length - i - 1];
       }
       return newArray;
     }
 ```
Description: 

## Part 2 - `grep`
Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose. To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works. Also consider asking ChatGPT!

For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

1. -v or --invert-match
   a)
Explanation: Invert the sense of matching, to select non-matching lines.
   b)
Explanation:
3. -i or --ignore-case
   a)
Explanation: Ignore case distinctions in both the PATTERN and the input files.
   b)
Explanation:
5. -n or --line-number
   a)
Explanation: Prefix each line of output with the line number of that line within the input file.
   b)
Explanation:
7.  -o, --only-matching
   a)
Explanation: Show only the part of a matching line that matches PATTERN
   b)
Explanation:

Sources: https://man7.org/linux/man-pages/man1/grep.1.html
