# Lab Report 4
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

## Inforamtion

### File & Directory Structure 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/cb69b259-d1db-4623-ae83-5ed94c298e49)

### Contents of each file
**ListExamples.java </br>**
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/51298f7b-2486-4266-9254-890680d3e44b)
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/1291aa57-5800-4094-9597-55e34947fece)

**TestListExamples.java </br>**
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/fff12f4c-dfef-4ef2-bb72-bc917db282a6)

**bash.sh** </br>
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/3cfa393a-ad8b-442a-8e1e-8172c2538bb4)


### Command line (or lines)
`bash.sh` 

### Fixing the bug
1. Change Line 43: ` result.add(list1.get(index1-1));` --> ` result.add(list2.get(index2));`

## Reflection: 
I really enjoyed getting famiilar with Vim, because it is efficient and convenient. I don't need an IDE to view my files, and I do not need to have multiple windows to edit my code. Also being able to control everything from my keyboard eliminates time that a mousepad would take. Since it is lightweight, it starts quickly and can handle large files. Finally, it can run on every operating system and doesn't need a bunch of configurations, editors, extensions to run and edit different files written in different languages. 
