# Lab Report 2
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Part 1
A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Failure inducing input - 
Input that doesn’t induce a failure - 



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
