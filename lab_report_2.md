# Lab Report 2
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Part 1

### String Server Code: 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/8c87549b-92e7-4435-85a5-24304ad3dfd1)

### Output after `/add-message?s=Hi` command: 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/57dc3c4a-9ad6-43bb-a606-d33a472f7ad3) <br>

#### Which methods in your code are called?
**StringServer main method:**
- String[].length --> args.length
- System.out.println()
- Integer.parseInt()
- Server.start()

**StringServer handleRequest method:**
- URI.getPath().equals() --> url.getPath().equals()
- StringBuilder.toString() --> output.toString()
- URI.getPath().contains() --> url.getPath().contains()
- URL.getQuery().split --> url.getQuery().split()
- String.equals() --> parameters[0].equals()
- StringBuilder.append() --> output.append()
- StringBuilder.toString() --> output.toString()

#### What are the relevant arguments to those methods, and the values of any relevant fields of the class?
**StringServer main method:**
- String[].length --> args.length: no arguments
- System.out.println(String: `"Missing port number! Try any number between 1024 to 49151"`)
- Integer.parseInt(String: args[0] = `4000`)
- Server.start(int: `port`, URLHandler: `new Handler()`)

**StringServer handleRequest method:**
- URI.getPath().equals() --> url.getPath().equals(String: `"/"`)
- StringBuilder.toString() --> output.toString(): no arguments
- URI.getPath().contains() --> url.getPath().contains(String: `"/add-message"`)
- URL.getQuery().split --> url.getQuery().split(String: `"="`)
- String.equals() --> parameters[0].equals(String: `"s"`)
- StringBuilder.append() --> output.append(String: "(int: `myInt`= `1`)+ ". " + String: `parameters[1]` = `"Hi"` + "\n"") = `1. Hi\n`
- StringBuilder.toString() --> output.toString(): no arguments

#### How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
**Values of relevant fields:**
- int myInt = 1 
- StringBuilder output = new StringBuilder()

**Values after relevant fields got changed:** 
- int myInt = 2
_Every time something is appended to the StringBuilder output, `myInt` increases by 1 to keep track of which number the messages is on the output list. `myInt` gets incremented in the handleRequest function everytime the url is entered followed by `/add-message` in a browser or using the curl command. Since it was initially 1, it will increment to 2, so that the next message inputted will be the second on the list._

- StringBuilder output = "1. Hi\n"
__String Builder output stores all of the inputted messages and displays it. Since only 1 message has been inputted, it stores the current value of `myInt` which is 1, followed by a period, the entered message (`parameters[1]`) and a newline character at the end of the current string stored in it (the current value of the string is null). This new message is "1. Hi\n"._

### Output after `/add-message?s=Hello%20World` command: 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/7d98fe96-61a6-4f10-8d73-1a72e36eb338) <br>

#### Which methods in your code are called?
**StringServer main method:**
- String[].length --> args.length
- System.out.println()
- Integer.parseInt()
- Server.start()

**StringServer handleRequest method:**
- URI.getPath().equals() --> url.getPath().equals()
- StringBuilder.toString() --> output.toString()
- URI.getPath().contains() --> url.getPath().contains()
- URL.getQuery().split --> url.getQuery().split()
- String.equals() --> parameters[0].equals()
- StringBuilder.append() --> output.append()
- StringBuilder.toString() --> output.toString()

#### What are the relevant arguments to those methods, and the values of any relevant fields of the class?
**StringServer main method:**
- String[].length --> args.length: no arguments
- System.out.println(String: `"Missing port number! Try any number between 1024 to 49151"`)
- Integer.parseInt(String: args[0] = `4000`)
- Server.start(int: `port`, URLHandler: `new Handler()`)

**StringServer handleRequest method:**
- URI.getPath().equals() --> url.getPath().equals(String: `"/"`)
- StringBuilder.toString() --> output.toString(): no arguments
- URI.getPath().contains() --> url.getPath().contains(String: `"/add-message"`)
- URL.getQuery().split --> url.getQuery().split(String: `"="`)
- String.equals() --> parameters[0].equals(String: `"s"`)
- StringBuilder.append() --> output.append(String sequence: "(int: `myInt`= `2`)+ ". " + String: `parameters[1]` = `"Hello World"` + "\n"") = `2. Hello World\n`
- StringBuilder.toString() --> output.toString(): no arguments

#### How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

**Original values of relevant fields:**
- int myInt = 3
- StringBuilder output = "1. Hi\n 2. Hello World\n"

How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

**Relevant fields that got changed:**
- int myInt = 3
_Every time something is appended to the StringBuilder output, `myInt` increases by 1 to keep track of which number the messages is on the output list. `myInt` gets incremented in the handleRequest function everytime the url is entered followed by `/add-message` in a browser or using the curl command. Since it was 2 after the message "Hi" was added, it will increment to 3, so that the next message inputted will be the third on the list._

- StringBuilder output = "1. Hi\n 2. Hello World\n"
__String Builder output stores all of the inputted messages and displays it. Since 1 message has already been inputted, it stores the current value of `myInt` which is 2, followed by a period, the entered message (`parameters[1]`) and a newline character at the end of the current string stored in it. This new message is "2. Hello World\n" which is added to the orginal message "1. Hi\n" changing the value of `output` to "1. Hi\n 2. Hello World\n"._

---
## Part 2

### Path to my private key for your SSH key:
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/52a63f24-62e9-4191-88f5-01ecf0c40893)

### Path to my public key for your SSH key:
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/c5bf392c-8b38-47a1-b169-d9557c18859e)

### Logging into my ieng6 through the terminal without being asked for a password:
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/802c4090-13c7-4ed1-a8d5-cf206b94e644)

---
## Part 3
#### Week 2 and 3 Reflection
This was the first time I had ever connected to a remote server before. So learning about my RSA IDs and port numbers was very unfamiliar but really interesting to learn becasue it helped me contextualize how web servers worked and how remote computers interacted with each other. It was also the first time I explored the concept of servers and so understanding how a server processes a URL was very helpful becuase it reduced my intimidation and fear towards working with servers.  Although I know that the Server.java code is far more simplifed than any server applications I interact with on a daily basis, it helped me understand on a fundamental what information is needed to build a server. It also exposed me to how a server breaks down a url and how it can pass the seperate parts of that url as arguments for different methods.

