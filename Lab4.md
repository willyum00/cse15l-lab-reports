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
keys pressed: ssh cs15lfa23bt@ieng6.ucsd.edu <enter> 
```

I used ssh to log in to a remote server from my machine to a machine at ucsd. 

## 5. Clone your fork of the repo using ssh url 
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/838de922-d527-44b6-984e-ffdd6c3ab07c)
```
keys presseD: git clone <ctrl> c <enter> (ctrl + c to copy paste the ssh link) 
```

I used git clone along with ssh url of my fork to clone the repo into my remote machine. I am able to do this because I have set up the ssh connection between my machine and ieng6. 

## 6. Run the tests, demonstrating that they fail

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/565441ac-b418-4416-ae52-dbd5a9668694)

```
cd lab7 <enter>
<up><up><up><up><up><up><enter> (javac was 6 steps above)
<up><up><up><up><up><up><enter> (java was 6 steps above)

```

## 7. Edit the code file ListExamples.java to fix the failing test

```
vim ListExamples.java <enter> 
44$ enter (I knew that the line to fix the error at would be at line 44 from previous experience)
<left><left><left><left><left><left>
x
i
1
<esc>
:wq
```

## 8. run the tests successfully 
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/05e36d44-6996-4e73-9745-0d9a2b4b61ce)

```
<up> <up> <up> <enter>
<up> <up> <enter> 

```

## 9. commit changes

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/f6396057-2c6b-4d8c-a41f-a6062dc5830d)

```
git add ListExamples.java <enter>
git commit -m 'lab report 4 demo fix' <enter> 
```

