## **Lab Report 3**

### The Grep Command

### Basics
The `grep` command stands for "**g**lobal search for **r**egular **e**xpression and **p**rint out". It searches a file for a particular pattern and displays all the lines that contain the pattern. The following is the syntax of the command:

`grep [options] pattern [files]`

One example of using grep command without any options is the following:
```
$ grep "command center" technical/911report/chapter-1.txt
  At 10:02 that morning, an assistant to the mission crew commander at NORAD's Northeast Air Defense Sector in Rome, New York, was working with his
colleagues on the floor of the command center. In a brief moment of reflection, he was recorded remarking that "This is a new type of war.
```
The grep command searches the lines of `chapter-1.txt` file in the `911report` directory for the phrase "command center" and displays the lines with that pattern. In this case, there is one line in the text file that has this pattern.


### Command-Line Options
The `grep` command has various command-line options, but here are four important ones. To show how these options function, we will use files and directories from `./technical`.

<br>

1. **-c option** displays only a count of the lines that match a pattern

**Example 1** 
```
$ grep -c "command center" technical/911report/chapter-1.txt
1
```
As we seen in the beginning, there is only one line in the chapter-1.txt file that matches the pattern "command center" exctly. Therefore the grep command with the -c option prints 1. 

**Example 2**
```
$ grep -c "BMI" technical/biomed/1468-6708-3-1.txt* 
32
```
There are 32 lines in 1468-6708-3-1.txt* file that matches the pattern "BMI". Therefore grep command with the -c option prints 32.

<br>

2. **-i option** ignores case sensitivity for matching.

**Example 1**
 ```
$ grep "command center" technical/911report/chapter-1.txt > 911_results.txt 
$ wc 911_results.txt
       1      51     290 911_results.txt
$ grep -i "command center" technical/911report/chapter-1.txt > 911_results2.txt
$ wc 911_results2.txt 
      34    2147   13592 911_results.txt
 ```
At first, the grep command only found one line in chapter-1.txt that matched the pattern "command center", but when the -i flag option was used, the grep command found 34 lines. This is because the command ignored case sensitvity and thus displayed all lines consisting of the pattern in some form (lowercase and uppercase).

**Example 2**
```
$ grep "cardiovascular" technical/biomed/1468-6708-3-1.txt
        trials to detect survival differences or cardiovascular
          cardiovascular disease (prevalent heart disease,
$ grep -i "cardiovascular" technical/biomed/1468-6708-3-1.txt
        trials to detect survival differences or cardiovascular
          Study design: The Cardiovascular Health
          The Cardiovascular Health Study (CHS) is a
          cardiovascular disease (prevalent heart disease,
        CHS Cardiovascular Health Study
```
The first grep command displays two lines from 1468-6708-3-1.txt file as they match the pattern "cardiovascular" exactly, whereas the the second grep comand with the -i option displays five lines as it ignores case sensitivity. For example, -i option causes the command to display lines with "Cardiovascular" as it matches the pattern without considering the uppercase and lowercase letters. 

<br>

3. **-v option** displays all the lines that do not matches the pattern

**Example 1**
```
$ grep -v "e" technical/plos/journal.pbio.0020001.txt

  
    
      
        
        
          
          
        
      
      
        2002).
        
          
            Canada?
          
        
      
      
        programs.
      
      
        journals (
        In 
      
      
        world.
        
          
          
        
        built.
      
    

$ grep -v "e" technical/plos/journal.pbio.0020001.txt > grep_results.txt
$ wc grep_results.txt
      35       8     330 grep_results.txt
```
The grep command with option -v displays lines that don't contain the pattern "e" from the journal.pbio.0020001.txt file. Using the wc command, we discovered that 35 lines, most of which are empty, didn't have the inputted pattern.

**Example 2** 
```
$ grep -v "a" technical/biomed/1468-6708-3-1.txt

  
    
      
        Introduction
        elderly [ 9 ] .
      
      
        
          Study
        
        
        
        
          ] .
          (for persons who were never in excellent, very good, or
          report results using only the simpler definition.
          findings.
        
        
        
        
        
      
      
        Results
        likely.
        from 25 to 29.9. The second column, which shows results
        under 20.
        groups.
        YOL or YHL.
      
      
        Discussion
        
        
        
          YHL.
        
        
        
      
      
        Conclusion
        'overweight' by the NHLBI guidelines. This suggests using
      
      
        Competing interests
      
      
        CESD Center for Epidemiologic Studies Depression
        poor?
      
    
  
$ grep -v "a" technical/biomed/1468-6708-3-1.txt > grep_results.txt
$ wc grep_results.txt
      55      65     848 grep_results.txt
```
The grep command with option -v displays lines that don't contain the pattern "a" from the 1468-6708-3-1.txt file. Using the wc command, we discovered that 55 lines, majority of which are empty, didn't have the inputted pattern.

<br>

4. **-l option** displays list of file names only

**Example 1** 
```
$ grep -l "programming" technical/biomed/*  
technical/biomed/1471-2105-1-1.txt
technical/biomed/1471-2105-2-8.txt
technical/biomed/1471-2105-2-9.txt
technical/biomed/1471-2105-3-12.txt
technical/biomed/1471-2105-3-18.txt
technical/biomed/1471-2105-3-30.txt
technical/biomed/1471-2105-4-28.txt
technical/biomed/1471-213X-1-12.txt
technical/biomed/1471-2148-1-1.txt
technical/biomed/1471-2156-4-9.txt
technical/biomed/1471-2253-2-5.txt
technical/biomed/1471-2288-3-9.txt
technical/biomed/1471-230X-1-10.txt
technical/biomed/1472-6807-2-4.txt
technical/biomed/1472-6807-2-9.txt
technical/biomed/1472-6904-2-5.txt
technical/biomed/1472-6947-2-7.txt
technical/biomed/1472-6947-3-5.txt
technical/biomed/1475-2875-1-14.txt
technical/biomed/1475-925X-2-1.txt
technical/biomed/1475-925X-2-11.txt
technical/biomed/1476-4598-1-8.txt
technical/biomed/gb-2001-2-10-research0041.txt
technical/biomed/gb-2001-2-4-research0012.txt
technical/biomed/gb-2001-2-6-research0021.txt
technical/biomed/gb-2002-3-11-research0065.txt
technical/biomed/gb-2002-3-12-research0081.txt
technical/biomed/gb-2002-3-12-research0082.txt
technical/biomed/gb-2002-3-3-research0011.txt
technical/biomed/gb-2002-3-7-research0032.txt
technical/biomed/gb-2003-4-1-r7.txt
```
The grep command with -l option displays all the file names of the files which contain the pattern "programming" from the biomed directory.

**Example 2** 
```
$ grep -l "police" technical/911report/*
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-3.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
```
The grep command with -l option displays all the file names of the files which contain the pattern "police" from the 911report directory.

#### Cited Sources
https://www.geeksforgeeks.org/grep-command-in-unixlinux/ <br>
https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix


