LabReport3 <br> 
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
 United States Senate Finance Committee hearing on rofexocib,
 the FDA, ...
From https://git-scm.com/docs/git-grep

-R command recursively searches for the term "Korea" in all
files within the ./technical directory. It is helpful for
finding occurrences of a pattern for many files and dir.

```

```
# code block (Grep -Rc)
grep -Rc "error" ./technical
Example: $ grep -Rc "He" ./technical
Output:
./technical/plos/pmed.0020246.txt:7
./technical/plos/pmed.0020247.txt:2
./technical/plos/pmed.0020249.txt:4
./technical/plos/pmed.0020257.txt:1
./technical/plos/pmed.0020258.txt:0
./technical/plos/pmed.0020268.txt:0
./technical/plos/pmed.0020272.txt:2
./technical/plos/pmed.0020273.txt:0
./technical/plos/pmed.0020274.txt:1

Example: $ grep -Rc "She" ./technical./technical/plos/pmed.0020239.txt:0
./technical/plos/pmed.0020247.txt:0
./technical/plos/pmed.0020249.txt:0
./technical/plos/pmed.0020257.txt:0
./technical/plos/pmed.0020258.txt:0
./technical/plos/pmed.0020268.txt:0
./technical/plos/pmed.0020272.txt:0
./technical/plos/pmed.0020273.txt:0
./technical/plos/pmed.0020274.txt:0
./technical/plos/pmed.0020275.txt:0
./technical/plos/pmed.0020278.txt:0
./technical/plos/pmed.0020281.txt:0

From https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_04_02.html
-Rc command count the occurrences of the term "He" in every files in ./techinal and it display the number of word count. 
```

```
# code block (Grep -F)
Example:
$ grep -Ri "Korea" ./technical
Output: 
./technical/government/Media man_on_national_team.txt:that document his days as a boxer, a Korean War veteran, a./technical/government/Media/Understanding.txt:Plans are to expand the effort to include Korean and Khmer, the ./technical/plos/journal.pbio.0020121.txt: imported cases in the Republic of Korea, but surveillance has not been thorough in North

Example: 
$ grep -Ri "United States" ./technical
Output:
./technical/plos/pmed.0020209.txt: “There is no
 independent voice for drug safety in the United States.”
 ./technical/plos/pmed.0020210.txt: Park, California, United States. At least one compound from this series is entering ./technical/plos/pmed.0020231.txt:        Rouge, Boston, and Saint Louis (all in the United States) have undertaken studies of 
 
 From https://linuxcommand.org/lc3_man_pages/grep1.html
grep -Ri command searches for the term "Korea" in techinical dir. It helps to find instances of a word regardless of its case, which can be helpful for case-insensitive searches.
```

```
# code block (Grep -o)
Example: 
$ grep -o "Korea" ./technical
Output: grep: ./technical: Is a directory

Example:
kfru1@ALEX MINGW64 ~/cs15l/lab3/Lab3-2/docsearch (main)
Out Put: $ grep -o "Korea" ./technical/911report/chapter-11.txt 
Korea
Korea

From https://linuxcommand.org/lc3_man_pages/grep1.html

for the first example output show up the the is a ./technical is a directory. and second example works thus, it's have to be file. 
```



