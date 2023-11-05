LabReport2 <br> 
HYEONJUN JUN <br>
A17181983 <br>
---
### PART 1 - Bugs

<br> # A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
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

<br> # An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
```
# code block (Error Input)
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}

  @Test
  public void testReversed() {
    int[] input1 = { 0 };
    assertArrayEquals(new int[]{ 0 }, ArrayExamples.reversed(input1));
  }
}
```

<br> # An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)


<img src= "https://github.com/kfru5515/cse15l-lab-reports-fa23/blob/main/Screenshot%202023-11-04%20114506.png?raw=true"/>

<br> # The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
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
```

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
<br> # Briefly describe why the fix addresses the issue.
<br> (reverseInPlace) the original code basically incomplited, it replaces each element with its corresponding element in the reversed position. Therefore, changed the elements are correctly swapped, ensuring that the array is reversed in place. and the loop goes up to length of 1/2 size. 

<br> (reversed) the original code implementation incorrectly assigned the elements of the array to their corresponding reversed positions, which resulted in overwriting half of the array with incorrect values. Threfore,  changed implementation correctly assigend the elements of the array to their reversed positions. 

### Part 2 - Researching Commands

```
# code block (Grep -R)
Example : grep -R "Korea" ./technical/
Out put : ./technical/911report/chapter-11.txt:               
in Korea another. But these were attacks by major powers.
 While by no means as ./technical/911report/chapter-11.txt:  
  the main focus (war in Korea), and as too unrealistic. As
   we pointed out in chapter ./technical/911report/chapter-12
   .txt: not experienced such a rapid surge in national
    security spending since the Korean ./technical/911report
    chapter-13.4.txt: Khallad, Aug. 13, 2003; Apr. 5, 2004.
     According to Khallad, Thailand, South Korea. ...

Example : grep -R "United States
Out put: ./technical/plos/pmed.0020206.txt: medical centers
 in the United States, yet I learned a great deal about these
  topics from ./technical/plos/pmed.0020208.txt:them was
   David Graham, Associate Director in the United States Food
    and Drug ./technical/plos/pmed.0020209.txt:testified at a
     United States Senate Finance Committee hearing on rofexocib, the FDA, ...
From https://git-scm.com/docs/git-grep

This command recursively searches for the term "Korea" in all
 files within the ./technical directory. It is helpful for
 finding occurrences of a pattern for many files and dir.

```

```
# code block (Grep -P)

<br>from https://www.gnu.org/software/grep/manual/grep.html
```

```
# code block (Grep -F)
<br>from https://linuxcommand.org/lc3_man_pages/grep1.html
```

```
# code block (Grep -O)
<br>Example
<br>

<br>from https://linuxcommand.org/lc3_man_pages/grep1.html
```



