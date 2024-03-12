# Lab Report 5

## Part 1:
### Student's post:
Hello, I have having trouble with Lab 7. I am trying to run the test file, it is showing multiple errors
and I am where these error are coming from and how to address them.
![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/69bad620-a3e9-4ebf-891f-f5dd58458ea7)

### TA's response:
Hello, thank you for reaching out. When reading the error message, it can be seen that there 2 error. Let's solve them one by one.
Try looking underneath the first error error (which is "1) testMerge1(ListExamplesTests)") and notice how a line specifies "ListExamples.merge(ListExamples.java:33)"?
I suggest using ```vim``` to access the file content for editing and look into what needs to be fixed. Good luck!

### Student's post:
It worked! I used ```vim``` to go into the ```listExamples.java``` file and navigated to line number 33 and traced the code around it. I noticed that after line 33, index2 needs to be update for the correct result. So since I am in ```vim``` I used ```i``` to insert ```index2+=1```. Then I clicked ```esc``` and enter ```:wp``` to save the edit and exit the file. Like shown below 
![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/5fb9ce85-b3d4-4241-ab82-1ac2f3505b20)
Then I ran ```bash test.sh``` to check in the first error was solved. When entered, it was indeed solved and I was left with my last error.
