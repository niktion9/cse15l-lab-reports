# Lab Report 3
## Part 1 - Bugs
> ### Failure Inducing input as a JUnit test:
```
public void testReverseInPlace() {
    int[] input1 = { 1, 2, 3, 4, 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1 }, input1);
}
```

> ### Input that does not induce a failure as a JUnit test:
```
public void testReverseInPlace() {
    //test that induces failure
    int[] input1 = { 1, 2, 3, 4, 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1 }, input1);


    //test that does not induce failure
    int[] input2 = {1, 1, 2, 1, 1};
    assertArrayEquals(new int[]{ 1, 1, 2, 1, 1 }, input1);
}
```

> ### Symptom of the tests
<img alt = "symptoms.jpg" src = "https://github.com/niktion9/cse15l-lab-reports/blob/main/symptoms.png?raw=true">

> ### Before and After code for Bug
Before: 
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
}
  }
```
After
```
static void reverseInPlace(int[] arr) {
    int[] tempArr = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      tempArr[tempArr.length - i - 1] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = tempArr[i];
    }
}
```
Explanation:
The bug in the code was that though it starts off by correctly reversing, this procedure is overwriting the elements of the array, so at one point of the iteration, the value in arr[i] and arr[arr.length - i - 1] will be the same bceause the original values of the elemnts needed for complete the reversing no longer exist as they were replaced towards the beginning of the iteration. This bug was fixed by creating a temporary array called ```tempArr```, into which the elements of the array parameter are coppied in reverse order. Then, with the help of another for loop, the elemnts values of ```tempArr``` are assignments to the respective indexes of ```arr```. This prevents any overwritten issues and sucessfully reverses the array. 

## Part 2 - The grep Command
The word ```grep``` stands for "global search for regualr expression". Like its full form, grep command is used for search for a particlar pattern/keyword in a specific space (like a file), both of these factors are given to the grep command as arguments. Then this command list information regarding the location of what is being searched.

### grep Command Option 1: ```-c```
Breif explanation: ```-c``` returns the number of lines that contain the specific pattern mentioned in the location given.
Example 1: 
```
nikitha@Nikithas-MacBook-Pro docsearch % cd technical
nikitha@Nikithas-MacBook-Pro technical % grep -c "President" government/About_LSC/conference_highlights.txt
5
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation: I used ```grep -c ``` and passed to the arguments "President" and "government/About_LSC/conference_highlights.txt" as the pattern to find and the location to find it in. This returned 5, showing that "President" was mentioned five times. This important because since the text file is about a highlights of a conference, I can figure out how many times a leader or important candidate's name is mentioned, rather than reading through the whole file. In a way it given a numerical summary about how much important information is there!

Example 2:
```
nikitha@Nikithas-MacBook-Pro technical % grep -c "lawyer" government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt government/About_LSC/LegalServCorp_v_VelazquezDissent.txt                        
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:5
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:10
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation: I used ```grep -c ``` and passed to the arguments "lawyer" and two files this time, which are "government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt" and "government/About_LSC/LegalServCorp_v_VelazquezDissent.txt" and as the pattern to find and the location to find it in. This returned 5, showing that "lawyer" was mentioned five times in the opinion file, and 10, showing that "lawyer" appeared ten times in dissent file. This is important because it once again saves time and makes reading multiple (more than one arguments can be given) long files more efficent by highlight how many key points including a lawyer are there.
Source: (https://www.geeksforgeeks.org/grep-command-in-unixlinux/) 

### grep Command Option 2: ```-l```
Breif explanation: ```-l``` returns the all the filenames that contain the specific pattern mentioned as an argument.
Example 1: 



