# Lab Report 1
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## `cd` command

1. **Command:** `[user@sahara ~]$ cd` <br>
   **Output:** Nothing

   **Working directory:** `/home` <br>
   **Explanation:** This was the first command I entered and since I had passed in no argments I had not moved into any directory. In order to move into a directory, `cd` needs the name of that directory passed into as as argument. `cd` also does not print any output. If I had already moved into a directory, `cd` would still not print any output. However the resulting directory after a `cd` command with no arguments would be the home directory.
   
   **Error?** No

3. **Command:** `[user@sahara ~]$ cd lecture1` <br>
   **Output:** Nothing

   **Working directory:** `/home/ <br>
   **Explanation:** I passed `lecture1` as an argument to the `cd` command. This directed `cd` to move into the directory and so the file path changed to add `lecture1`. `cd` also does not print any output. <br>
   **Error**? No

4. **Command:** `[user@sahara ~/lecture1]$ cd messages/zh-cn.txt` <br>
   **Output:** `bash: cd: messages/zh-cn.txt: Not a directory`

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** I passed `messages/zh-cn.txt` as an argument to the `cd` command. The working directory was `/home/lecture1` and within that there is a folder called `messages.` `messages` contains four files, one of which is `zh-cn.txt`. While `messages` is a valid directory, the path `messages/zh-cn.txt` is a file path and hence not a valid argument for the `cd` comment.  It is not possible to "move" into a file and so the error message is printed.  <br>
   **Error?** Yes

## `ls` command

1. **Command:** `[user@sahara ~/lecture1]$ ls` <br>
   **Output:** `Hello.class Hello.java messages README`

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** The command `ls` prints out the content within the file path. Since I was still in the `home/lecture1` directory, it printed the contents of that folder which include the `messages` folder, the `Hello.java` file, its corresponding `Hello.class` file, and finally the `README` file. <br>
   **Error?** No

2. **Command:** `[user@sahara ~/lecture1]$ ls messages` <br>
   **Output:** `en-us.txt es-mx.txt ko.txt. zh-cn.txt`

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** Ihe command `ls` also takes arguments. Here the argument was `messages` which is then added to the file path that indicates to the `ls` command what should be printed out. While we are still working in the `lecture1` directory, the `messages` folder is within the `lecture1` directory, allowing `ls` to access the `messages` folder and print out the content within that folder. <br>
   **Error**? No

3. **Command:** `[user@sahara ~/lecture1]$ ls messages/en-us.txt` <br>
   **Output:** `messages/en-us.txt`

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** I had passed `messages/en-us.txt` as an argument to the `ls` command. The working directory was still `/home/lecture1`. When the file path `messages/en-us.txt` is passed in, it allows `ls` to access the name of that file, without having to move into the `messages` directory. `ls` accepts filenames as arguments ands simply prints the file path relative to the working directory as the output. <br>
   **Error?** No

## `cat` command

1. **Command:** `[user@sahara ~/lecture1]$ cat` <br>
   **Output:** `                     ` 

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** The command `cat` expects a valid file path as an argument. Whatever is typed into the terminal after the command `cat` (with no arguments), will be printed out twice, until `Ctrl + C` is used to quit. `Ctrl + C` allows the next command line to be displayed. <br>
   For example:
   ![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/5c091e85-55b8-4e25-87ee-8c1475854897)

   **Error?** Yes, this is an error because the terminal does not inform the user that the arguments being inputted are invalid, nor does it tell them how to exit out of this never ending loop. Ideally the `cat` command should print an error message after no arguments have been passed in, requesting the user to pass in a valid file path.

3. **Command:** `[user@sahara ~lecture1]$ cat messages` <br>
   **Output:** `cat: messages: Is a directory`

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** Ihe command `cat` only takes file path as arguments. Here the argument was `messages` which is a directory and so the `cat` command cannot print out the content of a directory unless each file path is explicitly passed in as arguments. Therefore, the error message warns the user that they passed in a directory and not a file path.  
   **Error**? Yes

4. **Command:** `[user@sahara ~lecture1]$ cat Hello.Java` <br>
   **Output:** <br>

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/2ab113f0-b744-4646-9ee1-aca19ef41769)

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** I had passed ` Hello.Java` as an argument to the `cat` command. The working directory was still `/home/lecture1`. `cat` essentially prints out the content of a file, and so when that file was passed in, the content of that file is printed out which is shown in the image above. <br>
   **Error?** No
