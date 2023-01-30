# Servers and Bugs

## Web Server

StringServer code as a block

Image one of using /add
Image two of using /add

Describe after images

-Name of methods in my code

-Relevant arguments of those methods and values of relevant fields of the class

-How values of relevant fields of the class change from this specific request (given in instructions). I no values changed then explain why.

## Bugs

In lab 3, there was a bug with the method `testReverseInPlace()` that I was able to solve
Choose a bug from lab 3 and

The following JUnit test was a failure inducing input of the method:

```
@Test
public void testReverseInPlace() {
  int[] input1 = {3, 4, 5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5, 4, 3}, input1);
}
```

The following JUnit test was not a failure inducing input of the method:

```
@Test
public void testReverseInPlace() {
  int[] input1 = {3};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{3}, input1);
}
```

The associated code for both JUnit tests, that occured before the bug was fixed, was the method `reverseInPlace()`

```
static void reverseInPlace(int[] arr) {
    int[] tempArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      tempArray[0] = arr[i];
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

The symtpom of the failure inducing input mentioned above can been seen in the image below:

![Image](Lab2FailureSymptom)

The symtpom of the successful input mentioned above can been seen in the image below:

![Image](Lab2SuccessSymptom)

The following code is how the `testReverseInPlace()` code was written it was buggy:

```
static void reverseInPlace(int[] arr) {
    int[] tempArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      tempArray[0] = arr[i];
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

The following code is how the `testReverseInPlace()` code was written when the bug was fixed:

```
static void reverseInPlace(int[] arr) {
    int[] tempArray = new int[arr.length];
    for(int i = 0; i < arr.length/2; i += 1) {
      tempArray[0] = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = tempArray[0];
    }
  }
```

The way the changes fixed the issue where as follows. 

## Learning Experience

A few sentences describing something I learned from lab week 2 or 3 that I didn't know before.
