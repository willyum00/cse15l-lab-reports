# Lab 3 Report

## Part 1: Bugs

1. A failure inducing input for ArrayExamples
```java
@Test 
  public void testReversedInPlace(){
    int[] input = {1, 2, 3};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{3, 2, 1}, input);
  }
```

2. A non failure inducing input for ArrayExamples
```java
 @Test
  public void testReversedInPlaceEmpty(){
    int[] input = {};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{}, input);
  }
```

3. A screenshot of the symptom
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/2b7ed3e2-9982-40fc-854d-94da0ae629c3)

4. The bug

Original Code:
```java
   static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
Fixed Code:

```java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2 ; i += 1) {
      int j = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = j;
    }
  }

```

The bug in the original code was that there was no way for the "end" of the reversed version of the array to be filled. Halfway through the for loop, the array would repeat the first half of itself rather than reverse. I added a temporary variable to store the indexed value of the array and place it at the end, effectively swapping the front and end repeatedly. 
