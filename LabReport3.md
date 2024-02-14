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

## Part 2 - Researching Commands

