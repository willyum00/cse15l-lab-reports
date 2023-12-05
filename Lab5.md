# Lab Report 5 

## Part 1 - Debugging Scenario

### A conversation between a student and a TA. 
### Code is from Lab7's ListExamples.java

This is the file "pre-fix":

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/7f73446c-95b6-437e-a605-afc38c79af76)

I have underlined the bugs in the code causing the symptoms.

__student:__  I need help with finding the bugs in my ListExamples.java file. Here is a screenshot of the failed test: 

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/f3e5e0ee-db2a-429d-b586-ade9841ec4dc)

Test 1 tells me exactly which line is causing the error, so something written at that line is directly causing the error. Test 2 doesn't tell me which line is causing the error, which suggests that the code is running but the error is being caused by incorrect behavior. If I had to guess, the merge test is failing because of something wrong within the while loop? 

__TA:__ That's a good idea. Read the failure message for test1, and follow the line number it gives to find the error there. Do you notice any instructions to change anything there? Your idea for why test2 is failing is also good, it is probably a behavioral bug rather than a functional bug. Notice how the test2 error message says it expected [a] but got [c], which could suggest that the list was unintentionally reversed. Try to see if you can find where the ordering of the items in list is determined. 

__student:__  Here are the fixes I made. At line 44, there was indeed an instruction to change index1 to index2. For test2, I figured that since test1 fails at line 44, that means the outer while loop is triggered, so the symptom is probably not caused in the outer while loop. The two inner while loops are used to fill the list. Judging from the failure message, the lists have been filled, they are just in the wrong order. Thus, I determined that the bug was likely caused by the line:

 if(list1.get(index1).compareTo(list2.get(index2)) > 0) 

As this seems like the line where the order of the items in the list are determined. I changed the > to a <. I then ran the test again it passed. It seems the reason > was causing a behavioral issue was because list1.get(index1).compareTo(list2.get(index2)) gives a negative number if the string at index1 is lexographically less than the string at index 2 (i.e., a is lexographically less than c) and gives a positive number if the string at index1 is lexographically greater than the string at index 2. If the current direction (>) of the comparison operator were wrong, then it makes sense that this is probably causing the list order reversal. 
 

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/821001c3-4fc9-4c17-ae27-8f3250cabd87)

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/6eb68e2f-bb70-4a05-acb5-0f3ce9318bdd)

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/2a6d6f98-412f-4488-af3c-9f74bec9bfad)


## Part 2 - Reflection

Something cool I've learned is related to the way I work with github pages. The labs gave me a lot of confidence when it came to working with files related to website building, and I have been building my academic website using the knowledge I've learned in lab. I learned that you can actually preview a markdown page in vs code using ctrl + shift + v, and it automatically updates without having to switch between the code and preview section on github. The only drawback is images can't be directly copy pasted into the file, I'd have to recopy it later, but overall this made working with markdown very convenient. 
