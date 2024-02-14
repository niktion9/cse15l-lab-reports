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

