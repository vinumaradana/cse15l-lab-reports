## **Lab Report 3**

### The Grep Command

#### Basics
The `grep` command stands for "**g**lobal search for **r**egular **e**xpression and **p**rint out". It searches a file for a particular pattern and displays all the lines that contain the pattern. The following is the syntax of the command:

`grep [options] pattern [files]`

One example of using grep command without any options is the following:
```
$ grep "command center" technical/911report/chapter-1.txt
  At 10:02 that morning, an assistant to the mission crew commander at NORAD's Northeast Air Defense Sector in Rome, New York, was working with his
colleagues on the floor of the command center. In a brief moment of reflection, he was recorded remarking that "This is a new type of war.
```
The grep command searches the lines of `chapter-1.txt` file in the `911report` directory for the phrase "command center" and displays the lines with that pattern. In this case, there is one line in the text file that has this pattern.


#### Command-Line Options

Online, find 4 interesting command-line options or alternate ways to use the command you chose. For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

The `grep` command has various command-line options, but here are four important ones. To show how these options function, we will use files and directories from `./technical`.

1. -i option ignores case sensitivity for matching.

Example 1
 ```
$ grep "command center" technical/911report/chapter-1.txt > 911_results1.txt 
$ wc 911_results1.txt                                                       
       1      51     290 911_results2.txt
$ grep -i "command center" technical/911report/chapter-1.txt > 911_results2.txt
$ wc 911_results2.txt                                                          
      34    2147   13592 911_results2.txt
 ```
At first, the grep command only found one line in chapter-1.txt that matched the pattern "command center", but when the -i flag option was used, the grep command found 34 lines. This is because all these lines consisted of the pattern in some form (lowercase and uppercase) and the command ignored case sensitvity. 

Example 2
#### Cited Sources
https://www.geeksforgeeks.org/grep-command-in-unixlinux/
https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix


