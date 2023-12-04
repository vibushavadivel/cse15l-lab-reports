# Lab Report 5
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Original Post 
Hi! I am having trouble with the ListExamples `merge` function. For some reason, when I try to merge two lists, instead of getting a merged list, I am getting a list unorganized with the last element of the first list continuously repeating. 
</br> </br>
I feel like it has something to do in the second half of my merge function where I add the elements after the index of one of the lists is equal to or exceeds the length of the other list's size. If someone could help me debug this, that would be very helpful, thank you!

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/86928e05-a218-499b-8534-078a5406e0e0)

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/d6e0658e-ea01-4a9e-9491-2aeb3574a409)

## Response from a TA

Hi! It seems like when you are adding a value to your final merged list, you are adding from the wrong list. Since the number of final elements matches with the expected list, perhaps check the variable name you are using when you add it to your final merged list!


## Implementing TA's feedback
Original Code: </br>
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/e480ff81-684a-40ea-b0fb-829fcbc61b2e)

Thank you for this suggestion! I realized that I was actually adding the value from List1 under the List2 while loop. This is what was causing the repeated `orange` value. However, for some reason, the last element of my first list and first element of the second list are switched. Not sure what the big is in this, because all the elements are present, they just are not in the correct/expected order. </br>

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/d5470e01-9a2e-4239-89bb-6c063dbaace5)

## Information

### File & Directory Structure 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/cb69b259-d1db-4623-ae83-5ed94c298e49)

### Contents of each file
**ListExamples.java </br>**
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

  public static void main(String[] args) {
      ListExamples test = new ListExamples();
      List<String> list1 = new ArrayList<>(Arrays.asList("Apple", "Banana", "Orange"));
      List<String> list2 = new ArrayList<>(Arrays.asList("Grape", "Strawberry", "Papaya", "Pear"));

      List<String> result = test.merge(list1, list2);
      System.out.println(result.toString());

  }

}
```

**TestListExamples.java </br>**
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

      List<String> expected = (Arrays.asList("Apple", "Banana", "Orange", "Grape", "Strawberry", "Papaya", "Pear"));
      List<String> result = test.merge(list1, list2);
      System.out.println(result.toString());
      assertArrayEquals(expected.toArray(), result.toArray());

  }
}
```

**bash.sh** </br>
```
javac -cp ".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar" *.java
java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples > output.txt
echo "Tests ran sucessfully. The got the following output:"
grep -h "Failed :((" output.txt
grep -h "Passed!! :))" output.txt
```

### Command line (or lines)
`bash.sh` 

### Fixing the bug
1. Change Line 43: ` result.add(list1.get(index1-1));` --> ` result.add(list2.get(index2));`

## Reflection: 
I really enjoyed learning about VIM. The fact that it doesn't require an integrated development environment (IDE) for file viewing and doesn't need multiple windows to edit code editing makes it easier and more convenient. Also all the integrated keyboard shortcuts in Vim where almost every command is accessible through keyboard commands, minimizes the time-consuming nature of the mouse pad interactions, enhancing overall productivity. Its lightweight nature not only has a quick start up but also allows for large file handles, a great advantage for working on large databases. Furthermore, Vim's compatibility with every operating system eliminates the need for a bunch of of configurations, editors, or extensions to work with files written in different programming languages. The simplicity, speed, and universality of Vim have undoubtedly made it a valuable and efficient tool. 
