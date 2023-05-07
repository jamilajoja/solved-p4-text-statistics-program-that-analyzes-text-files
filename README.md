Download Link: https://assignmentchef.com/product/solved-p4-text-statistics-program-that-analyzes-text-files
<br>
<h1 id="project-title">P4: Text Statistics</h1>

<hr>

<h2 id="toc">Contents</h2>

<nav class="table-of-contents" role="navigation">

 <ul>

  <li><a id="link0" title="undefined" href="http://cs.boisestate.edu/~cs121/projects/p4/#part0">Project Overview</a></li>

  <li><a id="link1" title="undefined" href="http://cs.boisestate.edu/~cs121/projects/p4/#part1">Getting Started</a></li>

  <li><a id="link2" title="undefined" href="http://cs.boisestate.edu/~cs121/projects/p4/#part2">Specification</a></li>

  <li><a id="link3" title="undefined" href="http://cs.boisestate.edu/~cs121/projects/p4/#part3">Testing</a></li>

  <li><a id="link4" title="undefined" href="http://cs.boisestate.edu/~cs121/projects/p4/#part4">Submitting Your Project</a></li>

 </ul>

</nav>

<h2 id="part0">Project Overview</h2>

<section>

 In this program, you are going to implement a program that analyzes text files to generate some useful statistics. We will provide plain text versions of several books and articles (e.g. <em>Alice in Wonderland</em>, <em>The Gettysburg Address</em>, etc.) for you to analyze using your program.Text analysis is used in programs all the time. Your program will provide basic statistics like the number of characters, words, and lines, the average word length, and the number of each letter and word length. However, the same technique could be used to collect more statistics and create a program to ascertain characteristics of books and classify them for various purposes.




 Booklamp was a recent Boise startup (<strong>two of our CS department’s alumni were part of it!</strong>) that has created a sophisticated system for analyzing the text in books using techniques similar to what you will be doing in this lab. Booklamp software matches readers to books through an analysis of writing styles. The Booklamp technology allows us to find books that are written with a similar tone, tense, perspective, action level, description level and dialogue level. Booklamp was <a href="http://techcrunch.com/2014/07/25/apple-booklamp/">acquired by Apple on 25th July, 2014</a>.

 <h3>Objectives</h3>

 <ul>

  <li>Use <a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html">arrays</a>.</li>

  <li>Use command-line arguments.</li>

  <li>Read from text files using the Scanner class.</li>

  <li>Parse and analyze text input.</li>

  <li>Implement an interface.</li>

 </ul>

 <hr>

</section>

<h2 id="part1">Getting Started</h2>

<section>

 <ol>

  <li>Create a new Eclipse project for this assignment.</li>

  <li>The easiest way to import all the files into your project is to download and unzip the starter files directly into your project workspace directory (using the command-line or dolphin). The starter files are available here: <a href="http://cs.boisestate.edu/~cs121/projects/p4/stubs">http://cs.boisestate.edu/~cs121/projects/p4/stubs</a> (You should download <samp>p4-stubs.zip</samp>).</li>

  <li>After you unzip the files into your workspace directory outside of Eclipse, go back to Eclipse and refresh your project.</li>

  <li>Create <code>ProcessText</code> and <code>TextStatistics</code> classes in your project.</li>

  <li>Start by implementing <code>ProcessText</code>. You can ignore the command-line arguments to start. Just hard-code a file name so you can test your <code>TextStatistics</code> class as you write it. Create a <code>File</code> object and check to see that the file actually exists.

   <ul>

    <li>If the file <em>does exist</em>, your program will create a <code>TextStatistics</code> object for that file and print out the statistics for the file to the console.</li>

    <li>If the file <em>does not exist</em>, a meaningful error message needs to be printed to the user.</li>

   </ul></li>

  <li>Next you can start implementing <code>TextStatistics</code> according to the <a href="http://cs.boisestate.edu/~cs121/projects/p4/#TextStatistics">specifications</a>.</li>

  <li>At this point, you should go back and add command-line argument processing to <code>ProcessText</code> as described in the <a href="http://cs.boisestate.edu/~cs121/projects/p4/#ProcessText">specifications</a>. To make sure it correctly handles command line arguments, run it from the command line with no arguments, files that don’t exist, and files that do exist.</li>

  <li>Make sure to test your program thoroughly. We are giving you the <a href="http://cs.boisestate.edu/~cs121/projects/p4/#testing">test program and scripts</a> we will use to grade your program, so take advantage of this and make sure they pass!</li>

 </ol>

 <hr>

</section>

<h2 id="part2">Specification</h2>

<section>

 <h3>Project files</h3>

 For this assignment you are going to implement two classes. <code>TextStatistics</code> will be the class that reads a text file, parses it, and stores the information about the words and characters in the file. <code>ProcessText</code> is the driver class that gets a list of one or more filenames from the command line and collects statistics on each of the files using an instance of the <code>TextStatistics</code>object.

 <ul>

  <li>Classes that you will create: <samp>ProcessText.java</samp>, <samp>TextStatistics.java</samp></li>

  <li>Existing interface and class that you will use: <samp>TextStatisticsInterface.java</samp>, <samp>TextStatisticsTest.java</samp></li>

 </ul>

 You should be able to develop this program incrementally in such a way that you can turn in a program that runs even if you don’t succeed in implementing all the specified functionality.

 <h3 id="ProcessText">ProcessText.java</h3>

 <section>

  The driver class with the <code>main</code> method which processes one or more files to determine some interesting statistics about them.




  <ul>

   <li><h4>Command-line validation</h4>The names of the files to process will be given as command line arguments. Make sure to validate the number of command line arguments. There should be at least one file name given.If no files are given on the command line, your program must print a usage message and exit the program immediately. The message should read as follows.<pre>Usage: java ProcessText file1 [file2 ...]</pre>This lets the user know how they should run the program without having to go look up the documentation.</li>

   <li><h4>Processing command-line arguments</h4>If valid filenames are given on the command line, your program will process each command line argument by creating a <code>File</code> object from it and checking to see that the file actually exists.

    <ul>

     <li>If a file <em>does exist</em>, your program will create a <code>TextStatistics</code> object for that file and print out the statistics for the file to the console.</li>

     <li>If a file <em>does not exist</em>, a meaningful error message needs to be printed to the user. Continue processing the next file. An invalid file in the list should <strong>not</strong> result in the program crashing or exiting before all files have been processed.</li>

    </ul>The example, <a href="https://raw.githubusercontent.com/BoiseState/CS121-resources/master/examples/chap07/CmdLineArgs.java">CmdLineArgs.java</a>, shows how to use command line arguments in your program. The <code>args</code> parameter of the <code>main</code> method is an array of <code>String</code> objects that contains the command line arguments to the program. For your program, the array should contain the names of the files to be processed.</li>

  </ul>

  <h3 id="TextStatistics">TextStatistics.java</h3>

  <section>

   An instantiable class that reads a given text file, parses it, and stores the generated statistics.




   <ul>

    <li><h4>Implement the Interface</h4>Your <code>TextStatistics</code> class <strong>must</strong> implement the given <code>TextStatisticsInterface</code> (don’t modify the interface, it just provides a list of methods that your class must include).To implement an interface, you must modify your class header as follows<pre>public class TextStatistics implements TextStatisticsInterface{}</pre>Adding “implements TextStatisticsInterface” will cause an error in Eclipse. Select the quick fix option to “Add unimplemented methods” and it will stub out the required methods for you.</li>

    <li><h4>Instance variables</h4>Include a reference to the processed <code>File</code>. Include variables for all of the statistics that are computed for the file. Look at the list of accessor methods in the <code>TextStatisticsInterface</code> to determine which statistics will be stored.</li>

    <li><h4>Constructor</h4>Takes a <code>File</code> object as a parameter. The constructor should open the file and read the entire file line-by-line, processing each line as it reads it.

     <ul>

      <li>Your constructor needs to handle the <code>FileNotFoundException</code> that can occur when the <code>File</code> is opened in a <code>Scanner</code>. Use a <var>try-catch</var> statement to do this. Don’t just throw the exception.</li>

      <li>As each line is read, collect the following statistics:

       <ul>

        <li>The number of characters and lines in the file. The number of characters should include all whitespace characters, punctuation, etc. The number of lines should include any blank lines in the file.</li>

        <li>The number of words in the file.You must use a <code>Scanner</code> on each line to count the number of words in each line of the text file.<pre>private static final String DELIMITERS = "[\W\d_]+";</pre>Use <code>useDelimiter(DELIMITERS)</code> on your line <code>Scanner</code> to set the delimiters that the <code>Scanner</code> will use for separating words in the file.The scanner will not return any of the delimiter characters. For example, using <code>lineScan.next()</code> on the string.<pre>scheme, and the "plan" (for us)</pre>will give the following tokens.<pre>schemeandtheplanforus</pre>

         <aside>

          A note on words: Using the above delimiters might lead to strange words occasionally. For example, the contraction “we’ve” results in two words “we” and “ve.” This is okay and your program does not have to do anything to fix this.

         </aside>The <a href="https://raw.githubusercontent.com/BoiseState/CS121-resources/master/examples/file-io/UseScannerDelimiter.java">UseScannerDelimiter.java</a> example shows the different results you get using the default delimiters and user-specified delimiters.</li>

        <li>The number of words of each length that appears in the file. Assume that the maximum word length is 23. You do not need to print lengths that have a count of zero.</li>

        <li>The average word length for the file.</li>

        <li>The number of each letter that appears in the file – do not separate upper and lower case, just convert all characters to lower case before counting.See <a href="https://raw.githubusercontent.com/BoiseState/CS121-resources/master/examples/chap07/LetterCount.java">LetterCount.java</a> for a similar approach.</li>

       </ul></li>

     </ul></li>

    <li><h4>Getter (accessor) methods</h4>Implement the accessor methods for the number of characters, number of words, number of lines, average word length and for the arrays that contain the number of words of each length and the number of times each letter occurs in the file.

     <aside>

      If you implemented the interface correctly, you should already have methods for these. Just make sure they are returning the correct values. If you are doing your program correctly, most (if not all) of your accessor methods will just contain a single return statement.

     </aside></li>

    <li><h4>toString method</h4>Write a <code>toString()</code> method that generates and returns a <code>String</code> that can be printed to summarize the statistics for the file as shown in the <a href="http://cs.boisestate.edu/~cs121/projects/p4/#sampleSession">sample output</a>.</li>

   </ul>

   <hr>

  </section>

  <h2 id="part3">Testing</h2>

  <section>

   You must test your program thoroughly before submitting it. We will be using similar testing strategies when we grade your program, so you should have a good idea whether or not your code will pass our tests before submitting.




   <h3>TextStatisticsTest.java: Automated testing based on the interface.</h3>

   We have provided a test program that tests your <code>TextStatistics</code> class using three sample text files. This test program will not compile unless you have properly implemented the required interface. This is available in your starter files.

   <h3>autograde.sh: Testing based on program output.</h3>

   <dl>

    <dt>

     <samp>autograde.sh</samp>

    </dt>

    <dd>

     A shell script (a program made up of shell commands) that you can run to see if your program is going to work with the shell script used for grading the programs.

    </dd>

    <dt>

     <samp>testfile.txt</samp> and <samp>etext</samp>

    </dt>

    <dd>

     Sample text files used by <samp>autograde.sh</samp>

    </dd>

    <dt>

     <samp>testresults</samp>

    </dt>

    <dd>

     The expected output of <samp>autograde.sh</samp>. Your output should match the contents of this file.

    </dd>

   </dl>

   To use these files to test your program, copy them into your program directory on onyx and make sure that <samp>autograde.sh</samp> is executable. (Doing a <kbd>ls -l</kbd> on the file should give <kbd>-rwx------</kbd>. If the x is missing, type <kbd>chmod +x autograde.sh</kbd>).

   Now you run the test by typing

   <pre><kbd>./autograde.sh</kbd></pre>

   If your program does not compile and run, you need to fix it if you want any points for the program. Make sure all the files have the names specified.

   <hr>

   <h3 id="sampleSession">Sample Sessions</h3>

   <section>

    <h4>Sample output for bad arguments/non-existing files</h4>

    <pre><samp>[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="97eef8e2d7f8f9eeef">[email protected]</a> p4]$ java ProcessTextUsage: java ProcessText file1 [file2 ...][<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="3855594a514b4b597857564140">[email protected]</a> p4]$ java ProcessText not-a-file.txtInvalid file path: not-a-file.txt[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="f994988b908a8a98b996978081">[email protected]</a> p4]$ java ProcessText not-a-file.txt testfile.txtInvalid file path: not-a-file.txtStatistics for testfile.txt==========================================================11 lines79 words465 characters------------------------------ a = 27         n = 25 b = 1          o = 26 c = 11         p = 5 d = 10         q = 0 e = 33         r = 21 f = 9          s = 30 g = 7          t = 35 h = 24         u = 7 i = 25         v = 1 j = 0          w = 10 k = 2          x = 1 l = 18         y = 2 m = 5          z = 0------------------------------ length  frequency ------  ---------      1          3      2         13      3         24      4         13      5         10      6          2      7          5      8          3      9          1     10          3     11          2Average word length = 4.24==========================================================</samp></pre>

    <h4>Sample output for the input file testfile.txt</h4>

    <pre><samp>[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="dda4b2a89db2b3a4a5">[email protected]</a> p4]$ java ProcessText testfile.txtStatistics for testfile.txt==========================================================11 lines79 words465 characters------------------------------ a = 27         n = 25 b = 1          o = 26 c = 11         p = 5 d = 10         q = 0 e = 33         r = 21 f = 9          s = 30 g = 7          t = 35 h = 24         u = 7 i = 25         v = 1 j = 0          w = 10 k = 2          x = 1 l = 18         y = 2 m = 5          z = 0------------------------------ length  frequency ------  ---------      1          3      2         13      3         24      4         13      5         10      6          2      7          5      8          3      9          1     10          3     11          2Average word length = 4.24==========================================================</samp></pre>

    <h4>Expected output for TextStatisticsTest</h4>

    <pre><samp>[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="542d3b21143b3a2d2c">[email protected]</a> p4]$ java TextStatisticsTestTesting on data file:testfile.txtPassed! getCharCount()Passed! getWordCount()Passed! getLineCount()Passed! getAverageWordLength()Passed! Arrays frequenciesPassed! Letter frequenciesTesting on data file:etext/Gettysburg-Address.txtPassed! getCharCount()Passed! getWordCount()Passed! getLineCount()Passed! getAverageWordLength()Passed! Arrays frequenciesPassed! Letter frequenciesTesting on data file:etext/Alice-in-Wonderland.txtPassed! getCharCount()Passed! getWordCount()Passed! getLineCount()Passed! getAverageWordLength()Passed! Arrays frequenciesPassed! Letter frequencies</samp></pre>

   </section>

  </section>

  <h2 id="part4">Submitting Your Project</h2>

  <section>

   <h3>Documentation</h3>

   <section>

    <h4>Javadoc Comments</h4>

    If you haven’t already, add <strong>javadoc comments</strong> to your program. They should be located immediately before the class header and before each method. If you forgot how to do this, go look at the <a href="http://cs.boisestate.edu/~cs121/labs.php?lab=01#docs">Documenting Your Program</a> section from lab.

    <ul>

     <li>Have a class javadoc comment before the class.

      <aside>

       Your class comment must include the <code>@author</code> tag at the end of the comment. This will list you as the author of your software when you create your documentation.

      </aside></li>

     <li>Have javadoc comments before <em>every</em> method that you wrote. Comments must include <code>@param</code> and <code>@return</code> tags as appropriate.</li>

     <li>To build and view your comments, run the following commands.<pre><kbd>javadoc -author -d doc *.javagoogle-chrome doc/index.html<kbd></kbd></kbd></pre></li>

    </ul>

    <h4>README</h4>

    Include a plain-text file called <strong><big><tt>README</tt></big></strong> that describes your program and how to use it. Expected formatting and content are described in <a href="https://raw.githubusercontent.com/BoiseState/CS121-resources/master/projects/README_TEMPLATE.md">README_TEMPLATE</a>. See <a href="https://raw.githubusercontent.com/BoiseState/CS121-resources/master/projects/README_EXAMPLE.md">README_EXAMPLE</a> for an example.

   </section>

  </section>

 </section>

</section>

5/5 - (1 vote)

You should only have to read through each file once if you are doing this program properly. By the end of the constructor, the <code>TextStatistics</code> object should have collected all of its statistics and calls to its accessor methods will simply return the stored values.