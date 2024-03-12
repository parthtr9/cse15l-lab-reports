# **Lab Report 5** 
## Part 1 Debugging Scenario 
---
---
*Edstem Post:* <br>
 **Title:** Problem while running the test script, I wrote the correct code but the test is not passing. Is there something wrong with my tests?
 **Category** *skill demonstration* <br>
 I think I wrote the correct code based on the instructions but my tests are still failing, I tried writing new test cases to check but they are also failing. I can't find anything wrong with my code. Any help would be appreciated! Thanks!
 
<img width="1251" alt="image" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/abe62ce0-a008-4657-b62e-0efc1546c27a">

I am getting this error which shows both of the tests fail. 

---
*Reply* from **InstructorAdmin**:
Hi student, the test output says that it is failing on lines 12 and 19 of `ListExamplesTest.java`. Can you check what is being called at those lines? I would also appreciate if you could give more information as to what you are testing and how you have written the code as well as your workspace hierarchy.

---
*Reply* from **student**:
Hiii! Thanks for the response! After checking the `ListExamplesTest.java` file, `merge` is being called on both those lines from `ListExamples.java` file. 
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;
import java.util.ArrayList;


public class ListExamplesTests {
	@Test(timeout = 500)
	public void testMerge1() {
    		List<String> l1 = new ArrayList<String>(Arrays.asList("x", "y"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("a", "b"));
		assertArrayEquals(new String[]{ "a", "b", "x", "y"}, ListExamples.merge(l1, l2).toArray());
	}
	
	@Test(timeout = 500)
        public void testMerge2() {
		List<String> l1 = new ArrayList<String>(Arrays.asList("a", "b", "c"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("c", "d", "e"));
		assertArrayEquals(new String[]{ "a", "b", "c", "c", "d", "e" }, ListExamples.merge(l1, l2).toArray());
        }

}

```


> This is my code for `ListExamplesTests.java` file
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) > 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }


}

```


> This is the `ListExamples.java` file which contains the `merge` method at line 24.

```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```


> And this is my `test.sh` file which I run to compile and execute the files.

All these files are in the same directory named `lab7`.
Hope this information helps, please let me know if you need more material from my side.

Thanks a lot!

---

*Reply* from **InstructorAdmin**:
Thanks for the prompt reply student. I see that there is nothing wrong with your bash or `ListExamplesTest` file but I would recommend you to carefully look at your merge method, especially on the line where you use the `compareTo` method. Hope this helps!

---

*Reply* from **student**:
Ohh yeah I fixed the bug, it was such a silly mistake. Instead of checking if `list2.get(index2)` is greater than `list1.get(index1)`, I mistakenly wrote it the other way, checking if `list1.get(index1)` is greater than `list2.get(index2)`. Now after running the test script both the tests pass.
```
static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }
```
> This is the merge method after the fix.

---
<img width="1256" alt="image" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/023101bc-c98d-4892-9b63-39f02a7e2a84">

> The test.sh output after the fix. All tests pass successfully.

---
---

## Part 2 Reflection:
In the past weeks' lab I learned a lot of things that I did not know before like running `jdb` using terminal, creating new files and directories and using GitHub locally, but the coolest thing I learned has to be `vim`. At first, I was very confused as to how to use `vim` and what it was but using the `vimtutor` in lab helped me clear all those doubts and start understanding it. I am still astonished as to how easy it is to use `vim` and how diverse its applications are. Being able to do edit and correct a file from terminal is realy cool.

---
---
