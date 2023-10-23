## Lab 1 Report

In this report/post, I will be discussing some basic filesystem commands. 
Specifically: cd, ls, and cat

**1. What happens when you use these commands with no arguments?**

   a. Using cd without arguments resets the directory to the home directory.
   This is the conventional behavior for most terminals, but somtimes if there is no home directory, cd without arguments will do nothing. It is not an error. 

   b. Using ls without arguments prints a list of every file in your current directory. This is the conventional and expected behavior for ls without arguments, and it makes it easy to navigate through the paths. 
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/d7421301-efc5-475a-847d-1ae83a59690c)
   
   c. Using cat without arguments does nothing, as cat is used to print the contents of a file in text form. If you use no input for the cat command, it will read data from the standard input (the waiting terminal) and send it to the standard output. 
![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/4396f58d-1d4b-44f2-8f1f-bb198347cb77)
In order to exit, you have to manually terminate using ctrl + C.


**2. What happens when you use these commands with a path to a directory as an argument?**
   
   a. Using cd with a directory as an arguments puts you in that directory. Here, I am changing directory to the relative path lecture1/messages. It is a "relative" path because an absolute path would include the home directory, which I am currently in. 
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/bcf8de17-ba01-43eb-b9f5-907511a249a9)

   If you attempt to change to a relative path that is not immediately connected to your working directory, you get an error.
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/accc81c5-6dac-43f0-a0be-f0e17c0fdec6)


   b. Using ls with a directory as an argument will print the files in that directory. Here, I am listing the files of the relative path lecture1/messages. 

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/7cfd3dc1-c499-4338-bcb8-57a36ea4fdfb)

   c. Using cat with a directory will display an error message. This is because cat needs to be given a path to a file, not a directory. 

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/5cd9a51e-06d5-4f54-9b49-ae6783eca544)

**3. What happens when you use these commands with a path to a file as an argument? 

   a. Using cd with a path will throw a "not a directory" error. This is because cd can only take a directory (or nothing) as an argument. 

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/75c32eb6-d24c-45db-a445-0cf41dfe018e)

   b. Using ls with a path to a file will simply return the argument back to you. This is the conventional behavior because ls is used to list the contents in a directory, and files are not directories. 

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/346b16d6-385e-449e-bf23-472fc0b9bed0)

   c. Using cat with a path to a file will print the contents of that file. This is the expected behavior for cat. 

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/0873bc5e-156e-47a6-b44c-1bb58b44cdc3)

   






