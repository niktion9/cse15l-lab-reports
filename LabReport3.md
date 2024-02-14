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
> <img width="867" alt="Screen Shot 2024-01-30 at 5 23 55 PM" src="[https://github.com/niktion9/cse15l-lab-reports/assets/150311091/d4129384-f24f-46c4-bb0d-4aba38ad177f](https://github.com/niktion9/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-18%20at%202.16.18%20AM.png)https://github.com/niktion9/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-18%20at%202.16.18%20AM.png"/>

