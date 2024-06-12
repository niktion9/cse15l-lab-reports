# Lab Report 5

## Part 1:
### Student's post:
Hello TA, I am practing for Skill Demo 4 and I am stuck at step 3. I am trying to run the test file in the buggy directory with the ```test.sh``` command, and it is showing 2 errors as it should 
but I am not sure how to approach or understand the error messages and where to look for to fix, I am also not sure about what part of the code is inducing these failures. 
I would really appreciate some sort of a clue or guidance in solving this. Thank you!

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/6ed1e6f0-95ff-4186-920d-28838dcf8dd6)

### TA's response:
Hello! <br>
First off, when you re-read Step 3, at the beginning a file called ```ListExamples.java``` is mentioned. As you read the step further, more specfications on location, like the methods, within the file should give you a clue about where to look for! Like we learned in lab, you can use ```vim``` to access the file and make changes. 
With that being said, let's move on to understanding the error messages. The first line right below the first error message says ```org.junit.runners.model.TestTimedOutException: test timed out after 100 milliseconds```. A ```TestTimedOutException``` expection is thrown when a test takes longer to execute than a specified time period. It usually occurs in cases like infinite loops or any changes in code causing it to run for a long time. So, try looking for any iterations or lines of code related to them and analyze to find a mistake which is prolonging the execution time.

Now let's look at the second error. The first line right below the second error message says ```java.lang AssertionError: expected:< [apple, a] > but was:<[a, apple]>```. With the little expected result example mentioned, it can be seen that the file has code written in such a way where it adds elements to the beginning of the array, while the expected action is to be added to the end. So, a way to approach this error is by first looking any line of code that does the action fo appending, and if there are multiple, look for the one that specially add a certain element to the beginning. After spotting it, read the code around it to double check and attempt to alter to code statement accordingly.

Let me know if you have any questions. Good luck!

### Student's post:
I think I fixed the errors! I realized that in step 3, it was clearly indicated that within the ```ListExamples.java``` file, there are bugs in the ```filter``` and ```merge``` implementations. Thank you for pointing that out. I used ```vim``` to nagivate through ```ListExamples.java``` spotted where the first error was happening. It was in the ```merge``` method, specifically in it's last while loop, when ```index2``` and the size of ```list2``` are used and limitatations for the while loop. I noticed that instead of ```index2``` being incremented by one, ```index1```, thus ```index2``` is never reaching the index of last element of ```list2``` which keeps the loop going on forever. I used ```i``` to intiate the index feature and replaced ```index1 += 1``` to ```index2 += 1```. Here is a screenshot of my changes.

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/66ee2227-6d86-450f-958a-9ec339c9da2e)


Then, in the ```filter``` method, I was able to pin down the line of code, ```result.add (O, s)```. I read through the code and understood that this appending statement is reponsible for adding elements at the beginning of the array rather than the end. Since the insert feature is still active, i was able to chance the code from  ```result.add (O, s)``` to ```result.add (s)``` so it adds the element at the end of the array.
Here is another screenshot

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/5cb61365-b5f1-454e-a056-65ade9f9c1a2)

Then I clicked the ```esc``` button and typed ```:wp``` to save the changes and exit the file

Then, when I ran ```bash test.sh``` the code was no longer give me failures. Thanks!

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/137c1791-95b0-4653-bd37-7b9263449a46)

## Part 2:
I really enjoyed the lab where we had to do excercises from a textbook-like feature consisting of lessons about vim and all its different features, which we accessed on the terminal itself. The creation of that workbook itself was fascinating, and left me wondering about how making something like this was even possible. It also really helped me with my pratice and actual skill demo later, when I needed to use ```vim``` to quickly finish my tasks.
