## **Lab Report 2 - Servers and Bugs**

### Part 1: Creating a Web Server

Write a web server called StringServer that supports the path and behavior described below. It should keep track of a 
single string that gets added to by incoming requests. The requests should like th

`/add-message?s=<string>`


The following is my code for StringServer:

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // A string that will be manipulated by various requests.
    String output = "";

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                output += parameters[1] + "\n";
            }
        }
        return output;
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

After writing the code for StringServer, I altered the path to check that code produced the expected output as you can
see in the following snap shots.


For each of the two screenshots, describe:

- Which methods in your code are called?
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

By values, we mean specific Strings, ints, URIs, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.)

![Image](sserver1.png)
![Image](sserver2.png)

### Part 2: Bugs
Choose one of the bugs from lab 3.

Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

### Part 3: Reflection
In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn’t know before.

