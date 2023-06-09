LAB REPORT 5!

Ed-Stem Questions:

What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?
- I'm working on a MacBook Pro, my web browser is Chrome, and my terminal/editor is in VSCode

Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.
- The problem I'm running into is that the terminal is saying the file/class ListExamples can't be found. I expected the terminal to find the class and then the terminal would output that the tests I created in the TestListExamples.java file were successful and show that 4/4 of my tests passed. Below I copy and pasted my terminal output

//output begins here
```

RyLees-MacBook-Pro:list-examples-grader-1-main ryleedavis$ bash grade.sh
fatal: repository 'student-submission' does not exist
Finished cloning
ListExamples.java not found
Score: 0/4
cp: student-submission/ListExamples.java: No such file or directory
TestListExamples.java:6: error: cannot find symbol
class IsMoon implements StringChecker {
                        ^
  symbol: class StringChecker
TestListExamples.java:17: error: cannot find symbol
    List<String> merged = ListExamples.merge(left, right);
                          ^
  symbol:   variable ListExamples
  location: class TestListExamples
TestListExamples.java:26: error: cannot find symbol
    List<String> merged = ListExamples.merge(left, right);
                          ^
  symbol:   variable ListExamples
  location: class TestListExamples
TestListExamples.java:35: error: cannot find symbol
    List<String> filtered = ListExamples.filter(input, new IsMoon());
                            ^
  symbol:   variable ListExamples
  location: class TestListExamples
TestListExamples.java:43: error: cannot find symbol
    List<String> filtered = ListExamples.filter(input, new IsMoon());
                            ^
  symbol:   variable ListExamples
  location: class TestListExamples
5 errors
JUnit output was:
JUnit version 4.13.2
.E
Time: 0.002
There was 1 failure:
1) initializationError(org.junit.runner.JUnitCommandLineParseResult)
java.lang.IllegalArgumentException: Could not find class [TestListExamples]
        at org.junit.runner.JUnitCommandLineParseResult.parseParameters(JUnitCommandLineParseResult.java:100)
        at org.junit.runner.JUnitCommandLineParseResult.parseArgs(JUnitCommandLineParseResult.java:50)
        at org.junit.runner.JUnitCommandLineParseResult.parse(JUnitCommandLineParseResult.java:44)
        at org.junit.runner.JUnitCore.runMain(JUnitCore.java:72)
        at org.junit.runner.JUnitCore.main(JUnitCore.java:36)
Caused by: java.lang.ClassNotFoundException: TestListExamples
        at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
        at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
        at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:521)
        at java.base/java.lang.Class.forName0(Native Method)
        at java.base/java.lang.Class.forName(Class.java:495)
        at java.base/java.lang.Class.forName(Class.java:474)
        at org.junit.internal.Classes.getClass(Classes.java:42)
        at org.junit.internal.Classes.getClass(Classes.java:27)
        at org.junit.runner.JUnitCommandLineParseResult.parseParameters(JUnitCommandLineParseResult.java:98)
        ... 4 more

FAILURES!!!
Tests run: 1,  Failures: 1


--------------
| Score: 1/4 |
--------------
```
 //ouput ends here 
  
 Below is currently what my grade.sh file looks like which is the one I'm running with ```bash grade.sh```
  
 ```
  //grade.sh code begins here
  
 CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'


if [[ -e student-submission/ListExamples.java ]] 
    then echo "Submit correctly"

fi

// cp student-submission/* grading-area
if [ $? -eq 0 ]
    then echo "Files moved successfully to grading-area."

fi

cp student-submission/ListExamples.java ./

javac -cp $CPATH *.java

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 
  ```
 //grade.sh code ends here
  
  
Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.
  - Within the lab for week 9 I attempted to run the command ```bash grade.sh``` followed by cloning ```student-submission``` in the terminal in hopes that with the command ```cp student-submission/ListExamples.java ./``` or ```find ListExamples.java``` , where both attempts include the path and file name I'm looking for, would run and show in my directory. After that didn't work I continued to search for the file using ```ls``` and didn't see it still.  (shown an image below) 
  
 <img width="158" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/717c6300-0e02-4c67-8cda-817c358dea1a">
  
  
  
 TA Response: A possible reason to why the file you're looking for, ListExamples.java, is because both of your commands ```cp student-submission/ListExamples.java ./``` and ```find ListExamples.java``` is an error in the cloning and or importing process. Meaning that there's a possibility the ListExamples.java file was never imported successfully to the files you're accessing. And if the file was never imported successfully it would make sense as to why it doesn't show in your directory with the search commands you're using, and why the tests are ultimately failing. I would suggest the command that could re-import the files you're looking for. Once you do that, the command should hopefully clone ALL of the contents (including listExamples.java) and run grade.sh on them, after that I believe the tests should then pass successfully.
  
  
 Student Response After Trial (step 3) : 
  
  Thank you! You're explanation made a lot of sense and I'm seeing the output I expected now. Below is what I see in my terminal after using a command to import my files, which was ``` bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected``` and now 4/4 of my tests pass successfully. Your explanation helped me further solidify that because ListExamples.java wasn;t among my files the file couldn't be cloned and utilized in the process of grading ```student-submission``` . I also now see ListExamples.java in my sidebar (which I inserted a screenshot of below) which is a sure sign that I fixed the bug.
  
  
 // terminal output begins
 ```
RyLees-MacBook-Pro: % bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected
Cloning into 'student-submission'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
Finished cloning
Submit correctly
Files moved successfully to grading-area.
JUnit version 4.13.2
....
Time: 0.005

OK (4 tests)
```
  
//terminal output ends
  
 (picture of sidebar)
  
  
 <img width="157" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/54ebb1e3-4e3a-472c-bdd7-129050565908">
 
 
  
 Information Regarding the Setup (step 4):
 
 The error was that the file ListExamples.java never found which caused errors to follow and tests to fail. ListExamples.java was not found because the file was never imported successfully. After running the code ``` bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected``` it allowed for the files (including Listexamples.java) to be imported and cloned successfully in order for the grade.sh to run successfully and for all 4/4 tests to pass successfully as well. An example of the correct file contents is down below, because in the end it wasn't and issue in the file contents but in the import and cloning process which caused the absence of a neccessary file. 
  
  
  //Grade.sh code begins
  
  ```
  CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'


# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests
if [[ -e student-submission/ListExamples.java ]] 
    then echo "Submit correctly"

fi

# cp student-submission/* grading-area
if [ $? -eq 0 ]
    then echo "Files moved successfully to grading-area."

fi

cp student-submission/ListExamples.java ./

javac -cp $CPATH *.java

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 
  
  ```
  //Grade.sh code ends 
  
  
  //ListExamples.java code begins
  
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
        result.add(s);
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


}
 ```
 //ListExamples.java code ends 
 
 //GradeServer.java code begins 
 ```
 import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.URI;
import java.net.URISyntaxException;
import java.util.Arrays;
import java.util.stream.Stream;

class ExecHelpers {

  /**
    Takes an input stream, reads the full stream, and returns the result as a
    string.

    In Java 9 and later, new String(out.readAllBytes()) would be a better
    option, but using Java 8 for compatibility with ieng6.
  */
  static String streamToString(InputStream out) throws IOException {
    String result = "";
    while(true) {
      int c = out.read();
      if(c == -1) { break; }
      result += (char)c;
      System.out.println(System.currentTimeMillis() + "; just read: " + (char)c);
    }
    return result;
  }

  /**
    Takes a command, represented as an array of strings as it would by typed at
    the command line, runs it, and returns its combined stdout and stderr as a
    string.
  */
  static String exec(String[] cmd) throws IOException {
    Process p = new ProcessBuilder()
                    .command(Arrays.asList(cmd))
                    .redirectErrorStream(true)
                    .start();
    InputStream out = p.getInputStream();
    return String.format("%s\n", streamToString(out));
  }

}

class Handler implements URLHandler {
    public String handleRequest(URI url) throws IOException {
       if (url.getPath().equals("/grade")) {
           String[] parameters = url.getQuery().split("=");
           if (parameters[0].equals("repo")) {
               return ExecHelpers.exec(new String[]{"bash", "grade.sh", parameters[1]});
           }
           else {
               return "Couldn't find query parameter repo";
           }
       }
       else {
           return "Don't know how to handle that path!";
       }
    }
}

class GradeServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
//GradeServer.java code ends

//TestListExamples.java code begins 
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.Arrays;
import java.util.List;

class IsMoon implements StringChecker {
  public boolean checkString(String s) {
    return s.equalsIgnoreCase("moon");
  }
}

public class TestListExamples {
  @Test(timeout = 500)
  public void testMergeRightEnd() {
    List<String> left = Arrays.asList("a", "b", "c");
    List<String> right = Arrays.asList("a", "d");
    List<String> merged = ListExamples.merge(left, right);
    List<String> expected = Arrays.asList("a", "a", "b", "c", "d");
    assertEquals(expected, merged);
  }

  @Test(timeout = 500)
  public void testMergeLeftEnd() {
    List<String> left = Arrays.asList("a", "b", "z");
    List<String> right = Arrays.asList("a", "d");
    List<String> merged = ListExamples.merge(left, right);
    List<String> expected = Arrays.asList("a", "a", "b", "d", "z");
    assertEquals(expected, merged);
  }

  @Test(timeout = 500)
  public void testFilterSingle() {
    List<String> input = Arrays.asList("Moon", "MOO", "moo");
    List<String> expect = Arrays.asList("Moon");
    List<String> filtered = ListExamples.filter(input, new IsMoon());
    assertEquals(expect, filtered);
  }

  @Test(timeout = 500)
  public void testFilterMulti() {
    List<String> input = Arrays.asList("Moon", "MOO", "moon", "MOON");
    List<String> expect = Arrays.asList("Moon", "moon", "MOON");
    List<String> filtered = ListExamples.filter(input, new IsMoon());
    assertEquals(expect, filtered);
  }
}
```
//TestListExamples.java code ends
  




Reflection:
Something that I've taken away from my lab experience this quarter was how in depth debugging goes and how crucial it is when making programs. From all of the debugging scenarios in class to the ones made in lecture by accident, I've found that being able to break up code and criticially think about how and why a problem is occuring is an important yet difficult skill to learn. It's been cool to see different methods of debugging as well as different ways to check coe and crate tests (example: JUnit). Overall debugging is an interesting process that I was able to learn more about this quarter.
