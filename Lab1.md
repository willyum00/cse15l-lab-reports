In this report/post, I will be discussing some basic filesystem commands. 
Specifically: cd, ls, and cat

1. What happens when you use these commands with no arguments?

   a. Using cd without arguments resets the directory to the home directory.
   
    ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/163c6c65-d657-44ea-84b2-8e38d30313e0)

   b. Using ls without arguments prints a list of every file in your current directory.
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/d7421301-efc5-475a-847d-1ae83a59690c)
   
   c. Using cat without arguments does nothing, as cat is used to print the contents of a file in text form. If you give it nothing, it will print nothing. You have to manually terminate this command, likely because it is not designed to automatically terminate when given an empty input. 
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/b355692e-ca16-4405-b397-40bbff522ba1)

2. What happens when you use these commands with a directory as an argument?
   
   a. Using cd with a directory as an arguments puts you in that directory.
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/bcf8de17-ba01-43eb-b9f5-907511a249a9)

   b. Using ls with a directory as an argument will print the files in that directory.

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/7cfd3dc1-c499-4338-bcb8-57a36ea4fdfb)

   c. Using cat with a directory will display an error message, as cat needs to be given a path to a file.

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/5cd9a51e-06d5-4f54-9b49-ae6783eca544)

3. What happens when you use these commands with a path?

   a. Using cd with a path will throw a "not a directory" error. This is because cd can only take a directory (or nothing) as an argument. 

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/75c32eb6-d24c-45db-a445-0cf41dfe018e)

   b. Using ls with a path argument will print the path.

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/5ac09e3b-7eb4-4728-807d-4620b6894892)

   c. Using cat with a path to a file will print the contents of that file.

   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/0873bc5e-156e-47a6-b44c-1bb58b44cdc3)

   






