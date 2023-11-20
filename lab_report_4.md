# Lab Report 4
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## VIM 

### 1. Log into ieng6
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/d463149f-d704-4ea7-a5db-28640ceffc9d) 

**Keys Pressed:** ssh cs15lfa23hd@ieng6.ucsd.edu `<enter>` <br>

I typed out ssh and my ieng6 email to log in.

### 2. Clone your fork of the repository from your Github account (using the SSH URL)
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/7c81e2e6-4a9b-464d-a1e8-9ac73766f076)

**Keys Pressed:** git clone `<Ctrl> + V` `<enter>` <br>

I copied the ssh link to the repository i had forked, so I typed git clone and pasted to link to clone the repository.

### 3. Run the tests, demonstrating that they fail
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/e7862b34-87e7-4d05-8fd1-ffb40412a09d)
**Keys Pressed:** cd lab7, `<enter>`, `<Ctrl> + C`, `<Ctrl> + V`, `<enter>`, `<Ctrl> + C`, `<Ctrl> + V`, ListExamplesTests <br>
I moved into the lab7 directory and then copied and pasted the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command to compile the file. I then 
copied the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` and then typed in ListExamplesTests to run the file.

### 4. Edit the code file to fix the failing test
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/4cdfff7b-e22d-402c-81e6-af0679dbc9e9)
**Keys Pressed:** vim `<Ctrl> + C`, `<Ctrl> + V`, `<enter>`, `k`x6, `l`x11, `i`, 2, `<esc>`, `l`, `x`, `:wq` <br>
I typed vim and then copy and pasted the file name "ListExamples.java" to open the file in vim. Then I typed `k` six times to move my cursor up to the line with the bug. 
Then I typed `l` eleven times to move my cursor so that it would hover over the character "1". Then I typed `i` so that I could insert "2" next to the character "x". Then I 
clicked `<esc>` to return to Normal mode on vim and clicked `l` so that my cursor would move one to the right to hover over "1". Then I typed `x` to delete the character "1". 
Finally I typed `:wq` to save the file (`w`) and quit VIM (`q`).

### 5. Run the tests, demonstrating that they now succeed
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/00212eb1-5bd8-4cb1-a874-1ee0d90ac6c2)
**Keys Pressed:** `<up>`x2, `<enter>`, `<up>`x3, `<enter>` <br>

The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was up 2 commands in the search history, so I typed the up arrow 2 times to access it. The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` was up 3 commands in the search history, so I typed the up arrow 3 times to access it. 

### 6. Commit and push the resulting change to your Github account (you can pick any commit message!)
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/e74160ed-fcda-4a5a-9b3f-325933e19a1b)

**Keys Pressed:** git add ., git commit -m "changed index1 to index2 in last loop of merge", git push origin main <br>

I typed those three commands to commit and push my changes to my GitHub account. First I added made sure that I included all changes with `.` operator. 
Then I committed those changes and added a message. Finally, I pushed them to the origin repository in main.

