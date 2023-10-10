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
   **Explanation:** This was the first command I entered and since I had passed in no argments I had not moved into any directory. In order to move into a directory, `cd` needs the name of that directory passed into as asn argument. `cd` also does not print any output. 
   **Error?** No

2. **Command:** `[user@sahara ~]$ cd lecture1` <br>
   **Output:** Nothing

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** I had passed `lecture1` as an argument to the `cd` command. This directed `cd` to move into the directory and so the file path changed to add `lecture1`. `cd` also does not print any output. <br>
   **Error**? No

3. **Command:** `[user@sahara ~]$ cd messages/zh-cn.txt` <br>
   **Output:** `bash: cd: messages/zh-cn.txt: Not a directory`

   **Working directory:** `/home/lecture1` <br>
   **Explanation:** I had passed `messages/zh-cn.txt` as an argument to the `cd` command. The working directory was `/home/lecture1` and within that there is a folder called `messages.` `messages` contains four files, one of which is `zh-cn.txt`. While `messages` is a valid directory, the path `messages/zh-cn.txt` is a file path and hence not a valid argument for the `cd` comment.  You cannot "move" into a file and so the error message is printed.  <br>
   **Error?** Yes

## `ls` command

## `cat` command
