## Lab Report 5

### Part 1 – Debugging Scenario
For this lab report, I created my code from scratch. I created two files, `ArraySort.java` and `ArrayTests.java`, and a bash script, `test.sh`.

The following is the file and directory structure:

![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/f6126154-a78d-4087-9087-5ef32db50e47)

**Post in EdStem: Student's Bug**
*What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?*
macOS (operating system); VScode (editor); Chrome (browser) 

*Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.*


After running the `bash test.sh ArrayTests`, I recieved the following output:  
![image](Screenshot 2023-06-05 at 8 20 00 PM" src="https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/80444a56-30ba-4918-b43f-7916b93320a8")

One test is failing because of an Index Out of Bounds error. However, all the test cases are expected to pass. The arrays sorted using my sort() method should match the ones that are sorted by the built-in sorting algorithm. 

*Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.*

The following are the contents of my files and my bash script:

The content of `ArraySort.java` file: 
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/ac009229-7bf2-452a-a4fe-6987946ae7ce)

The content of `ArrayTests.java` file:
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/d46cb1ce-4ceb-4edc-9421-630aa34c773c)

The content of the bash script used to run the tests in `ArrayTests.java` 
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/498743b5-f76e-454c-8a30-16e9546340b8)

**TA's Response**
What part of your code could lead to an Index Out of Bounds error? Hint: Check the line number where the error resulted in. More specifically, which part of the for loop involves the index?

**Student's Reflection**
Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.

According to the previous output, the error originated in line number 9, which compares the numbers located in indices `i` and `j` in `arr`. Then, I looked more closely at the for loops and realized the bug was a typo in the inner for loop header. I wrote `i < arr.length` instead of `j < arr.length`. This resulted the `i` to be 1 greater than it's supposed to be, causing an Index Out of Bounds error when calling `arr[i]`.


At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug

You should actually set up and run the scenario from your screenshots. It should involve at least a Java file and a bash script. Describing the bug should involve reading some output at the terminal resulting from running one or more commands. Design an error that produces more interesting output than a single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.

### Part 2 – Reflection
In a couple of sentences, describe something you learned from your lab experience in the second half of this quarter that you didn’t know before. It could be a technical topic we addressed specifically, something cool you found out on your own building on labs, something you learned from a tutor or classmate, and so on. It doesn’t have to be specifically related to a lab writeup, we just want to hear about cool things you learned!

Something cool I learned from my lab experience is how the autograder, which grades our PAs in our other classes, is created and why it works the way it does. It was interesting to see how the skills we learned in this class, including commands, vim and bash script, can be applied to create something like an autograder. 
