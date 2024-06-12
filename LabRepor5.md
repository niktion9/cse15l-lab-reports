# Lab Report 5

## Part 1:
### Student's post:
Hello TA, I am practing for Skill Demo 4 and I am stuck at step 3. I am trying to run the test file in the buggy directory with the ```test.sh``` command, and it is showing 2 errors as it should 
but I am not sure how to approach or understand the error messages and where to look for to fix, I am also not sure about what part of the code is inducing these failures. 
I would really appreciate some sort of a clue or guidance in solving this. Thank you!

![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/6ed1e6f0-95ff-4186-920d-28838dcf8dd6)

### TA's response:
Hello! <br>
First off, when you read the very beginning line of the very next step 4, a file called ```ListExamples.java``` is mentioned. As you read the step further, more specfications on location, like the methods, within the file should give you a clue about where to look for! Like we learned in lab, you can use ```vim``` to access the file and make changes. 
With that being said, let's move on to understanding the error messages. The first line right below the first error message says ```org.junit.runners.model.TestTimedOutException: test timed out after 100 milliseconds```. A ```TestTimedOutException``` expection is thrown when a test takes longer to execute than a specified time period. It usually occurs in cases like infinite loops or any changes in code causing it to run for a long time. So, try looking for any iterations or lines of code related to them and analyze to find a mistake which is prolonging the execution time.

Now let's look at the second error. The first line right below the second error message says ```java.lang AssertionError: expected:< [apple, al > but was:<[a, apple]>```. With the little expected result example mentioned, it can be seen that the file has code written in such a way where it adds elements to the beginning of the array, while the expected action is to be added to the end. So, a way to approach this error is by first looking any line of code that does the action fo appending, and if there are multiple, look for the one that specially add a certain element to the beginning. After spotting it, read the code around it to double check and attempt to alter to code statement accordingly.

Let me know if you have any questions. Good luck!

### Student's post:
