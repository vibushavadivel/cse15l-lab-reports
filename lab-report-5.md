# Lab Report 5
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Original Post 
**[Student]:** Hi! I am having trouble with the ListExamples `merge` function. For some reason, when I try to merge two lists, instead of getting a merged list, I am getting a list unorganized with the last element of the first list continuously repeating. I feel like it has something to do in the second half of my merge function where I add the elements after the index of one of the lists is equal to or exceeds the length of the other list's size. If someone could help me debug this, that would be very helpful, thank you!

**Input:** 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/41e92bd5-a677-40a0-bd32-af3a7a32b1b5)

**Output:**
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/441b1b2d-49fa-47db-a600-2d91110216bf)


## Response from a TA

**[TA]:** Hi! It seems like when you are adding a value to your final merged list, you are adding from the wrong list. Since the number of final elements matches with the expected list, perhaps check the variable name you are using when you add it to your final merged list!


## Implementing TA's feedback
**[Student]:** Thank you for this suggestion! I realized that I was actually adding the value from List1 under the List2 while loop. This is what was causing the repeated `orange` value. However, now the third element of the second list keeps repeating. Not sure what the error is...

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/fc78e7d2-3af9-495d-95a4-f1dd24608856)

**[TA]:** Hm! Did you look at the argument you are passing in for the `add` command? Also make sure your inital while loop is not ending early and you are being consistent with how you are accessing and iterating through your elements. 

**[Student]:** Oh, I see. I didn't realize I used index1 when adding elements to List2. Just changed the argument `index1-1` to `index2`. It works as expected. Thank you for all your help! :)

## Information

### File & Directory Structure 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/cb69b259-d1db-4623-ae83-5ed94c298e49)

### Contents of each file
**ListExamples.java**
```
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list1.get(index1-1));
      index2 += 1;
    }
    return result;
  }

}
```

**TestListExamples.java**
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.Arrays;
import java.util.List;

class IsMoon implements StringChecker {
  public boolean checkString(String s) {
    return s.equalsIgnoreCase("moon");
  }
}

public class TestListExamples {
  
  public void testMergeRightEnd() {
    List<String> left = Arrays.asList("a", "b", "c");
    List<String> right = Arrays.asList("a", "d");
    List<String> merged = ListExamples.merge(left, right);
    List<String> expected = Arrays.asList("a", "a", "b", "c", "d");
    assertEquals(expected, merged);
  }

  @Test
  public void testMerge() {

      ListExamples test = new ListExamples();
      List<String> list1 = Arrays.asList("Apple", "Banana", "Orange");
      List<String> list2 = Arrays.asList("Grape", "Strawberry", "Papaya", "Pear");

      List<String> result = test.merge(list1, list2);
      System.out.println(result.toString());

      List<String> expected = (Arrays.asList("Apple", "Banana", "Orange", "Grape", "Strawberry", "Papaya", "Pear"));
      assertArrayEquals(expected.toArray(), result.toArray());

  }
}
```

**bash.sh**
```
javac -cp ".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar" *.java
java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples > output.txt
echo "Tests ran sucessfully. The got the following output:"
grep -h "Failed :((" output.txt
grep -h "Passed!! :))" output.txt
```

### Command line (or lines)
1. `cd Vibusha 2023/CSE 15L/lab-report-9`
2. `bash.sh` 

### Fixing the bug
1. Change Line 43: ` result.add(list1.get(index1-1));` --> ` result.add(list2.get(index2));`

## Reflection: 
I really enjoyed learning about VIM. The fact that it doesn't require an integrated development environment (IDE) for file viewing and doesn't need multiple windows to edit code editing makes it easier and more convenient. Also all the integrated keyboard shortcuts in Vim where almost every command is accessible through keyboard commands, minimizes the time-consuming nature of the mouse pad interactions, enhancing overall productivity. Its lightweight nature not only has a quick start up but also allows for large file handles, a great advantage for working on large databases. Furthermore, Vim's compatibility with every operating system eliminates the need for a bunch of of configurations, editors, or extensions to work with files written in different programming languages. The simplicity, speed, and universality of Vim have undoubtedly made it a valuable and efficient tool. 
