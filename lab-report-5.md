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

Thank you for this suggestion! I realized that I was actually adding the value from List1 under the List2 while loop. This is what was causing the repeated `orange` value. However, for some reason, the last element of my first list and first element of the second list are switched. Not sure what the big is in this, because all the elements are present, they just are not in the correct/expected order.
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/3365667f-8c78-4ab5-897c-4544bba74f2a)


At the end, all the information needed about the setup including:
The file & directory structure needed
lib 

Arraylists file
bash.sh 

The contents of each file before fixing the bug


The full command line (or lines) you ran to trigger the bug
bash.sh 

A description of what to edit to fix the bug


You should actually set up and run the scenario from your screenshots. It should involve at least a Java file and a bash script. Describing the bug should involve reading some output at the terminal resulting from running one or more commands. Design an error that produces more interesting output than a single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.
