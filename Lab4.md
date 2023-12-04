# Lab Report 4 

I will be documenting all key presses for steps 4 - 9 for the following: 

1. Setup Delete any existing forks of the repository you have on your account
1. Setup Fork the repository
1. The real deal Start the timer!
1. Log into ieng6
1. Clone your fork of the repository from your Github account (using the SSH URL)
1. Run the tests, demonstrating that they fail
1. Edit the code file ListExamples.java to fix the failing test (as a reminder, the error in the code is just that index1 is used instead of index2 in the final loop in merge)
1. Run the tests, demonstrating that they now succeed
1. Commit and push the resulting change to your Github account

## 4. Log into ieng6
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/52b1db48-ec1c-454e-ae34-1ea49b766bbc)
```
keys pressed: ssh cs15lfa23bt@ieng6.ucsd.edu <enter> (ssh stands for secure shell)
```

#### I used ssh to log in to a remote server from my machine to a machine at ucsd. It is a command use to access another computer remotely. The url I gave it is an ieng6 computer that I access from my own computer. 

## 5. Clone your fork of the repo using ssh url 
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/838de922-d527-44b6-984e-ffdd6c3ab07c)
```
keys pressed: git clone <ctrl> c <enter> (ctrl + c to copy paste the github repo ssh link) 
```

#### I used git clone along with ssh url of my fork to clone the repo into my remote machine. I am able to do this because I have set up the ssh connection between my machine and ieng6. 

## 6. Run the tests, demonstrating that they fail

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/565441ac-b418-4416-ae52-dbd5a9668694)

```
cd lab7 <enter> (cd accesses the directory lab7)
<up><up><up><up><up><up><enter> (javac command was 6 steps above, so I pressed up 6 times to get to the javac command I had ran earlier)
<up><up><up><up><up><up><enter> (java command was 6 steps above so I pressed up 6 times to get to the java command I had ran earlier)

```
#### cd lab7 changes the current directory to lab7/

#### javac -cp (classpath) *.java compiles all .java files within the lab7 directory. Because we are using junit hamcrest core for testing, we need to compile it with the lib path that tells the compiler where the junit and hamcrest core jar files are. 

#### java -cp (classpath) org.junit.runner.JunitCore ListExamplesTests runs the file ListExamplesTests.java. 
 
## 7. Edit the code file ListExamples.java to fix the failing test

```
vim ListExamples.java <enter> 
44$ <enter> 
<left><left><left><left><left><left> (I ended up somewhere I didn't expect, so I moved left 6 times to get to index1)
x
i
2
<esc>
:wq 

```

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/7dc397c0-039f-4d12-9e6d-7a54a336ed92)

#### vim ListExamples.java - I open the file in vim

#### 44$ - I knew that the line to fix the error at would be at line 44 from previous experience working with the file. After typing 44, vim is waiting for a command. I give it $, the line command, and it goes to line 44. 

#### x - deletes the character the cursor is currently at. I used x to delete "1" in index1.

#### i - switch to insert mode. I can now edit the file. 

#### 2 - I have already deleted "1", I now put "2" where 1 used to be.

#### <esc> - I exit insert mode and return to Normal mode. 

#### :wq - I save the file and quit



## 8. run the tests successfully 
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/05e36d44-6996-4e73-9745-0d9a2b4b61ce)

```
<up> <up> <up> <enter> (javac command was 3 steps above, so I press up 3 times to get to it)
<up> <up> <enter>  (java command was 2 steps above, so I press up 2 times to get to it)

```
#### javac -cp (classpath) *.java compiles all .java files within the lab7 directory. Because we are using junit hamcrest core for testing, we need to compile it with the lib path that tells the compiler where the junit and hamcrest core jar files are. 

#### java -cp (classpath) org.junit.runner.JunitCore ListExamplesTests runs the file ListExamplesTests.java. 

#### After the fix, the tests now pass!

## 9. commit changes

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/7b7ca742-f7bd-4efc-b18d-503238a4361a)

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/fcafc8bd-f2bc-45c3-9380-78d006adfdd6)



```
git add ListExamples.java <enter>
git commit -m 'lab report 4 demo fix' <enter> 
git push
```

#### git add (filename) --- adds a change in the working directory to the "staging area." In this case, we add the file ListExamples.java, which we edited. 

#### git commit -m "message" --- commits the files in the staging area to the original repository. The -m option allows me to add a message for the commit. 

#### git push --- pushes the changes the repository, which is now updated. 
