# Lab Report 5

## Part 1:
### Student's post:
Hello, I have having trouble with Lab 7. I am trying to run the test file, it is showing multiple errors
and I am not sure where these error are coming from and how to address them.

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/69bad620-a3e9-4ebf-891f-f5dd58458ea7)

### TA's response:
Hello, thank you for reaching out!
When reading the error message, it can be seen that there 2 errors. Let's solve them one by one.
Start by looking underneath the first error error (which is ```1) testMerge1(ListExamplesTests)```). Notice how a line specifies "ListExamples.merge(ListExamples.java:33)"? This is a great indication of where the error is coming from. I suggest going into the file and read he code at line 33 and aroud it to get an idea of where and what the actual bug is.
You can try using ```vim``` to access the file content and even for editing once you find the bug. 
Trying running the test file again, and repeat this process for debugging the second error as well. Please feel free to let me know if you have any questions or would like further guidance. Good luck!

### Student's post:
It worked! I used ```vim``` to go into the ```listExamples.java``` file and navigated to line number 33 and traced the code around it. I noticed that after line 33, index2 needs to be updated for the correct result. Because that was missing, and since I am in ```vim```, I used ```i``` to insert ```index2+=1```. Then I clicked ```esc``` and enter ```:wp``` to save the edit and exit the file. Like shown below 

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/5fb9ce85-b3d4-4241-ab82-1ac2f3505b20)


Then I ran ```bash test.sh``` to check in the first error was solved. When entered, it was indeed solved and I was left with my last error. This can be seen below:

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/b8908b08-9d99-4cae-b2d0-8d65b1c225a0)


I used the same appraoch as my pervious error and I figured out that the big was in the ```ListExamples.java``` at line 43. When I used ```vim``` to access the file conent, I noticed that the big was more specifically at line 45, where ```index1``` was being updated when ```index2``` was compared in the respective if conditional statement, instead of ```index2```. I used ```i``` to insert ```index2``` (Like shown below). Then I clicked ```esc``` and enter ```:wq``` to save the edit and exit the file. 

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/33774312-23dc-4484-9886-70574e23d00a)


## Part 2:
While the auto grader was the coolest project we did in lab, the most memorable and fun lab expreice for me would be during Week 2 and Week 3 when ww were working on building local servers. URLs are something we use every single day and actually learning about them and manipulating them was just fascnination. With so much new vocabular and commands, it was also one of the first times I interacted with all of my group and the TA. I remember happy like a kid when the server finally worked and I was able to update the number how many ver times wanted. While I think wiggling my legs happily in the chair was silly, I also think it is justifiable because it is rear that my code work within the first few tries. I also have a feeling that I will be building more servers in the future, and I will never forget how ,much I learned about it in this class.

