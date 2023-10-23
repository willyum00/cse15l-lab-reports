# Lab 2 Report

## part 1

In this lab, we build a webserver called StringServer.

code screenshot:

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/da0a5db5-20d9-4ef6-971a-263d65682209)


screenshots of using /add-message:
screenshot set 1:

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/84801dd5-ccb2-4092-9c7c-0d3725b5d889)
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/590f26cb-6981-4fd7-995d-0b9f80a6b2a8)

*Which methods are called?*
the handleRequest method is called. The relevant argument is the URI. Values of relevant fields include a stringBuilder to contain the query message, in this first case it's /add-message?s=screenshot. 
There is also an ArrayList that holds the requests in string form, initially empty, now populated by the string "screenshot", and int messageCounter, which tracks the request number 1., 2., etc. In this case, messageCounter changes from 0 to 1. 

screenshot set 2:

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/389c2dde-3a26-48e2-84ae-8fd83b01df8c)

*Which methods are called?*
the handleRequest method is called. The relevant argument is the URI. Values of relevant fields include a stringBuilder to contain the query message, in this second case it's /add-message?s=wassup. 
There is also an ArrayList that holds the requests in string form, initially only having the string "screenshot", now also has 
"wassup". And int messageCounter, which tracks the request number 1., 2., etc. In this case, messageCounter changes from 1 to 2. 


## Part 2 
**using ls, show path to private ssh key on computer:**

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/5f1569b9-1c08-440f-89db-a3b89d85a4f5)

**show path to public ssh key on ieng6 account:**

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/0f14ab0e-ed4a-4f67-be8b-49aa6704cb61)



**logging in without password:**

![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/ab6392fb-6acf-4422-a753-05f82315fe32)

## Part 3
**describe something you learned week2/3 that you didn't know before**

In week 2, I learned that in java, URI's are handled with specific libraries, and it is not as simple as taking parts of a url and encoding them as strings. I guess it's a bit obvious, 
but I had never thought of how it worked before. In order for my simple StringServer to work, I needed to have multiple interfaces and classes implemented before I could implement my StringServer
Class. 
