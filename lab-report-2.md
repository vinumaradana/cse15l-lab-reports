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
For this part, I chose the averageWithoutLowest method in ArrayExamples.java file in lab 3, whose code is listed below.  

```
  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```

To identify a failure-inducing input for the buggy program, I examined the logic of the code and brainstormed a test that will produce an error message and reveal the bug of the program. The following is a part of an example of a failure-inducing input from ArrayTests.java:

```
    double[] failureInducingInput = {8.0, 6.0, 10.0, 6.0};
```

The following is part of an example of an input that doesn’t induce a failure:

```
    double [] input = {2.0, 8.0, 10.0, 4.0};
```

The J-Unit test with both the inputs is the following:
```
 @Test
  public void averageWithoutLowest() {
    double[] failureInducingInput = {8.0, 6.0, 10.0, 6.0};
    double [] input = {2.0, 8.0, 10.0, 4.0};
    assertEquals(8.0, ArrayExamples.averageWithoutLowest(failureInducingInput), 1e-15);
    assertEquals(6.0, ArrayExamples.averageWithoutLowest(input), 1e-15);

  }
```

Next, I found the symptom or the output of running the tests by running the following commands in the terminal of my VS code.

```
local $ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
local $ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
```

The symptom of the averageWithoutLowest method can be seen below:
![Image](symptom.png)

The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

### Part 3: Reflection
In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn’t know before.

