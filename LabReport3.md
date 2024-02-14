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
Breif explanation: ```-l``` returns the all the filenames out of the onces entered, which contain the specific pattern that is also mentioned as an argument.

Example 1: 
```
nikitha@Nikithas-MacBook-Pro technical % grep -l "September 11" 911report/chapter-1.txt 911report/chapter-2.txt 911report/chapter-3.txt
911report/chapter-1.txt
911report/chapter-3.txt
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation: I used ```grep -l ``` where I search for "September 11" in three different files. This command returns the files (out of the ones mentioned) that actually contain the date. This is helpful because now the user knows which file is look at rather than searching through all the dozen of them.

Example 2:
```
nikitha@Nikithas-MacBook-Pro technical % grep -l "September 11" 911report/*                                                            
911report/chapter-1.txt
911report/chapter-10.txt
911report/chapter-11.txt
911report/chapter-12.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-3.txt
911report/chapter-5.txt
911report/chapter-7.txt
911report/chapter-8.txt
911report/chapter-9.txt
911report/preface.txt
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation: From the previous example, I realized how the file entered at only a few of many so I used ```grep -l ``` in another, samarter way by including ```*```
This way, I am able to search all of the 9/11 readings and find which files specifically have the date in them.
Source: (https://www.geeksforgeeks.org/grep-command-in-unixlinux/) 

### grep Command Option 3: ```-n```
Breif explanation: ```-n``` returns the line number and the line of the entered file, in which the given pattern in found.

Example 1: 
```
nikitha@Nikithas-MacBook-Pro technical % grep -n "Bill Clinton" 911report/chapter-11.txt
153:            Whatever the weaknesses in the CIA's portraiture, both Presidents Bill Clinton and
```
Explanation: ```grep -n```, with the given paramters return the line number and the whole line in the Chapter 11 text file where "Bill Clinton" was mentioned. This is helpful because it does not just give me the line number, but also the line number, so that I may not even need to nagivate to tej file to gain a little context about Bill Clinton.

Example 2:
```
nikitha@Nikithas-MacBook-Pro technical % grep -n "Bill Clinton" 911report/chapter-11.txt 911report/chapter-3.txt 
911report/chapter-11.txt:153:            Whatever the weaknesses in the CIA's portraiture, both Presidents Bill Clinton and
911report/chapter-3.txt:22:            President Bill Clinton ordered his National Security Council to coordinate the
911report/chapter-3.txt:1558:            President Bill Clinton's counterterrorism Presidential Decision Directives in 1995
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation:
When more than one file is entered as an argument, the output for the ```grep -n``` command mentioned the respective file name right before the line number. This is helpful as it allows you to search multiple files without the confusion regarding with line belongs to which file

Source: (https://superuser.com/questions/643788/what-does-grep-n-option-mean](https://man7.org/linux/man-pages/man1/grep.1.html)https://man7.org/linux/man-pages/man1/grep.1.html)


### grep Command Option 4: ```-e```
Breif explanation: ```-e``` returns the lines of the file entered, that match multiple patterns (more than one) that are mentioned as input

Example 1: 
```
nikitha@Nikithas-MacBook-Pro technical % grep -e "Bill Clinton" -e "Clinton" -e "President"  911report/chapter-11.txt
                President George H.W. Bush dealt with the first of these in 1990 and 1991 when he
            Whatever the weaknesses in the CIA's portraiture, both Presidents Bill Clinton and
                experts. In 1996, as a result of the TWA Flight 800 crash, President Clinton created
                a commission under Vice President Al Gore to report on shortcomings in aviation
                plane. One, a December 4 Presidential Daily Briefing for President Clinton
                President for rules of engagement, and there was no mechanism to do so. There was no
                for Operations James Pavitt gave an intelligence briefing to President-elect Bush,
                Vice President-elect Cheney, and Rice; it included the topic of al Qaeda. Pavitt
                is worth noting that they were made by the Clinton administration under extremely
                difficult domestic political circumstances. Opponents were seeking the President's
                impeachment. In addition, in 1998-99 President Clinton was preparing the government
            Officials in both the Clinton and Bush administrations regarded a full U.S. invasion
                We have found no indication that President Clinton was offered such an intermediate
                already discussed. Since we believe that both President Clinton and President Bush
            After 9/11, President Bush announced that al Qaeda was responsible for the attack on
            Earlier chapters describe in detail the actions decided on by the Clinton and Bush
                that consumed considerable time-especially in the Clinton administration- and
                for action offered to both President Clinton and President Bush.
                threatening the United States. The Clinton administration effectively relied on the
                2000, as part of a millennium after-action review. President Clinton and his
            Other agencies deferred to the FBI. In the August 6 PDB reporting to President Bush
                of 70 full-field investigations related to al Qaeda, news the President said he
                the FBI, yet during almost all of the Clinton administration the relationship
                between the FBI Director and the President was nearly nonexistent. The FBI Director
                would not communicate directly with the President. His key personnel shared very
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation: The ```grep -e``` command returned all the traces of "Bill Clinton", "Clinton", "President" present in the text of chapter 11. Though the output of this example is length, this is really helpful as the ```-e``` option allows you to specify what you looking for by entering multiple keywords.

Example 2:
```
nikitha@Nikithas-MacBook-Pro technical % grep -n -e "Bill Clinton" -e "Clinton" -e "President"  911report/chapter-11.txt
44:                President George H.W. Bush dealt with the first of these in 1990 and 1991 when he
153:            Whatever the weaknesses in the CIA's portraiture, both Presidents Bill Clinton and
217:                experts. In 1996, as a result of the TWA Flight 800 crash, President Clinton created
218:                a commission under Vice President Al Gore to report on shortcomings in aviation
225:                plane. One, a December 4 Presidential Daily Briefing for President Clinton
259:                President for rules of engagement, and there was no mechanism to do so. There was no
381:                for Operations James Pavitt gave an intelligence briefing to President-elect Bush,
382:                Vice President-elect Cheney, and Rice; it included the topic of al Qaeda. Pavitt
404:                is worth noting that they were made by the Clinton administration under extremely
405:                difficult domestic political circumstances. Opponents were seeking the President's
406:                impeachment. In addition, in 1998-99 President Clinton was preparing the government
427:            Officials in both the Clinton and Bush administrations regarded a full U.S. invasion
440:                We have found no indication that President Clinton was offered such an intermediate
443:                already discussed. Since we believe that both President Clinton and President Bush
466:            After 9/11, President Bush announced that al Qaeda was responsible for the attack on
472:            Earlier chapters describe in detail the actions decided on by the Clinton and Bush
474:                that consumed considerable time-especially in the Clinton administration- and
483:                for action offered to both President Clinton and President Bush.
525:                threatening the United States. The Clinton administration effectively relied on the
541:                2000, as part of a millennium after-action review. President Clinton and his
553:            Other agencies deferred to the FBI. In the August 6 PDB reporting to President Bush
554:                of 70 full-field investigations related to al Qaeda, news the President said he
758:                the FBI, yet during almost all of the Clinton administration the relationship
759:                between the FBI Director and the President was nearly nonexistent. The FBI Director
760:                would not communicate directly with the President. His key personnel shared very
nikitha@Nikithas-MacBook-Pro technical %
```
Explanation: Another example of the ```-e``` option is to use it with another option like ```-n```, which results in a more organized output. Along with the diverese lines of the text files about President Clinton, there are also line numbers which make it easier to refer to in the file.

Source: (https://superuser.com/questions/643788/what-does-grep-n-option-mean](https://man7.org/linux/man-pages/man1/grep.1.html)https://man7.org/linux/man-pages/man1/grep.1.html)

