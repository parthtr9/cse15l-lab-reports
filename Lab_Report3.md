# **Part 1**
## Bugs

1. A failure-inducing input:
   > code:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
   > input:
```
   @Test
  public void testReversed() {
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }
```

2. An input that doesn't induce a failure:
    > code:
    ```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
  >input:
```
@Test
  public void testReversed1() {
    int[] input1 = {1,2,1};
    assertArrayEquals(new int[]{1,2,1}, ArrayExamples.reversed(input1));
  }
```
