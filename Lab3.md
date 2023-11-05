# Lab 3 Report

## Part 1: Bugs

1. A failure inducing input for ArrayExamples
```java
 @Test 
  public void testAverageAllSame(){
    double[] input = {1, 1, 1, 1, 1};
    assertEquals(1.0, ArrayExamples.averageWithoutLowest(input), 0.0001);
  }
```

2. A non failure inducing input for ArrayExamples
```java
  @Test 
  public void testAverageWithoutNegative(){
    double[] input = {1, 2, 3, -4};
    assertEquals(2.0, ArrayExamples.averageWithoutLowest(input), .0001);
  }
```
