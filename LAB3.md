LabReport2 <br> 
HYEONJUN JUN <br>
A17181983 <br>
---
### PART 1 - Bugs
```
# code block (Error Input)
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
	}
//testReverseInPlace(ArrayTests)
//arrays first differed at element [2]; expected:<1> but was:<3>

  @Test
  public void testReversed() {
    int[] input1 = { 1,2,3,4 };
    assertArrayEquals(new int[]{ 4,3,2,1 }, ArrayExamples.reversed(input1));
  }
//arrays first differed at element [0]; expected:<4>but was:<0>
}
```

```
# code block (Original Code)
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  <br>
  <br>
  <br>
  <br>
```
<img src= "https://github.com/kfru5515/cse15l-lab-reports-fa23/blob/main/Screenshot%202023-11-04%20114506.png?raw=true"/>

```
# code block (Fixed Code)
  static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length / 2; i++) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i ++) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }


```

### Part 2 - Researching Commands



