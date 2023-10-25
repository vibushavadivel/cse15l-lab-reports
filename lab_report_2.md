# Lab Report 2
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Part 1

### String Server Code: 

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/8c87549b-92e7-4435-85a5-24304ad3dfd1)

### Output after `/add-message` command: 
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/57dc3c4a-9ad6-43bb-a606-d33a472f7ad3) <br>

_Which methods in your code are called? <br>_
StringServer main method:
- String[].length --> args.length
- System.out.println()
- Integer.parseInt()
- Server.start()

StringServer handleRequest methodt:
- URI.getPath().equals() --> url.getPath().equals()
- StringBuilder.toString() --> output.toString()
- URI.getPath().contains() --> url.getPath().contains()
- URL.getQuery().split --> url.getQuery().split()
- String.equals() --> parameters[0].equals()
- StringBuilder.append() --> output.append()
- StringBuilder.toString() --> output.toString()

What are the relevant arguments to those methods, and the values of any relevant fields of the class?
StringServer main method:
- String[].length --> args.length: no arguments
- System.out.println(String:"Missing port number! Try any number between 1024 to 49151")
- Integer.parseInt(String: args[0])
- Server.start(int: port, URLHandler: new Handler())

StringServer handleRequest methodt:
- URI.getPath().equals() --> url.getPath().equals(String: "/")
- StringBuilder.toString() --> output.toString()
- URI.getPath().contains() --> url.getPath().contains(String: "/add-message")
- URL.getQuery().split --> url.getQuery().split(String: "=")
- String.equals() --> parameters[0].equals(String: "s")
- StringBuilder.append() --> output.append(String sequence: "(myInt)+ ". " + parameters[1] + "\n"")
- StringBuilder.toString() --> output.toString(): no arguments

Relevant fields: 
- int myInt = 1
- StringBuilder output = new StrongBuilder()

How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
By values, we mean specific Strings, ints, URIs, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.)

![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/7d98fe96-61a6-4f10-8d73-1a72e36eb338) <br>
Which methods in your code are called?
What are the relevant arguments to those methods, and the values of any relevant fields of the class?
How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
By values, we mean specific Strings, ints, URIs, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.)

---
## Part 2

### Path to my private key for your SSH key:
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/52a63f24-62e9-4191-88f5-01ecf0c40893)

### Path to my public key for your SSH key:
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/ad057fb3-a1ca-444d-9c6a-9121070064b0)

### Logging into my ieng6 through the terminal without being asked for a password:
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/802c4090-13c7-4ed1-a8d5-cf206b94e644)

---
## Part 3
Week 2 and 3 Reflection



