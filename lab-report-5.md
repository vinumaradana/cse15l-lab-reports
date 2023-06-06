## Lab Report 5

### Part 1 – Debugging Scenario
For this lab report, I created my code from scratch. I created two files, `ArraySort.java` and `ArrayTests.java`, and a bash script, `test.sh`.

#### Post in EdStem: Student's Bug**

![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/d5b04e64-5beb-4c51-916a-9f21a3dd1bfc")
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/8210ce92-8e8c-402c-b6da-002ec35012af)
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/c305da42-3c9d-441d-9a38-1a8b2959cd44)
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/67acc6eb-6cf0-4032-b401-08ca7b7de9f1)

#### TA's Response
The error indicates there is an error in the logic of the sorting algorithm and thus, the values are not swapping properly. Thus, what part of the code could you alter to resolve this issue?

#### Student's Reflection
Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.

According to the previous output, two tests failed. First one failed because `arrays first differed at element [2]; expected:<4> but was:<1>` while the other one failed because `arrays first differed at element [1]; expected:<2> but was:<1>`. This shows that I didn't swap the values properly. After further examination, I realized that my lines 9 and 10 are in the wrong order. In this order, `temp` is storing the new value of `arr[i]` rather it's initial value. And, thus `arr[j]` is storing the new value of `arr[i]`, which is `arr[j]` itself. Thus, in this code `arr[i]` and `arr[j]` store the same value. 

To fix this, we need to swap lines 9 and 10 so that `temp` stores the initial value of `arr[i]` and the swapping occurs properly. After we resolved the bug, the following is the output. The output matches our expected output. 

![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/99329e55-412f-4300-8889-c1e07aba0916)



At the end, all the information needed about the setup including:

The following is the file and directory structure:
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/f6126154-a78d-4087-9087-5ef32db50e47)

The content of `ArraySort.java` file: 
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/615def05-7eba-4bd4-a433-b10ff45a8054)

The content of `ArrayTests.java` file:
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/5b84ac13-e54b-45b9-89eb-a5f21b8ab3a0)

The content of the bash script used to run the tests in `ArrayTests.java` 
![image](https://github.com/vinumaradana/cse15l-lab-reports/assets/127369782/498743b5-f76e-454c-8a30-16e9546340b8)

The full command line (or lines) you ran to trigger the bug:
`bash test.sh ArrayTests`

Description of what to edit to fix the bug:
Swap the lines 9 and 10 in the `ArraySort.java` file. So, the `temp` stores the initial value of `arr[i]` rather than the new value of `arr[i]`.

### Part 2 – Reflection
Something cool I learned from my lab experience is how the autograder, which grades our PAs in our other classes, is created and why it works the way it does. It was interesting to see how the skills we learned in this class, including commands, vim and bash script, can be applied to create something like an autograder.
