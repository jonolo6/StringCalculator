Pre-requisites
==============

1. Install GIT (http://git-scm.com/)
2. Create directory where to keep local copy of your project
3. Sync down the code.
	$> git clone https://github.com/jonolo6/StringCalculator.git
4. Import the project into your IDE
5. Install an Automatic test runner (TBD) so you don't have to run the unit tests manually all the time.
	- http://infinitest.github.com/ or http://junitmax.com/

How to use this Project
====================

Follow the TDD rules below to the best of your ability when working on this project:

1. You are not allowed to write any production code (anything under /src) unless it is to make a failing unit test pass.
2. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
3. You are not allowed to write any more production code (anything under /src) than is sufficient to pass the one failing unit test.

Follow the TDD flow below to the best of your ability when working on this project:

1. Write a failing test
2. Write code to make the test pass
3. Refactor the code.

The idea of the exercise is to do some deliberate practice, and improve your Refactoring skills. The idea is to re-write code from scratch and practice taking small steps, running the tests often, and incrementally improving the design.

Before you start
=================

    Try not to read ahead.
    Do one task at a time. The trick is to learn to work incrementally.
    Make sure you only test for correct inputs. there is no need to test for invalid inputs for this kata
	
Tips: 

* Let the IDEA do the work for you - creating tests (CMD - Shift - T in IntelliJ for instance)
* Refactor is the most important step to allow the code to grow well and nicely. 
	Take the time to refactor both source and test code in the TDD cycle.
* A Unit test should only test the class - mock all other dependencies using Mockito, etc.

String Calculator
=================

1. Create a simple String calculator with a method int Add(string numbers)
        1. The method can take 0, 1 or 2 numbers, and will return their sum (for an empty string it will return 0) for example “” or “1” or “1,2”
        2. Start with the simplest test case of an empty string and move to 1 and two numbers
        3. Remember to solve things as simply as possible so that you force yourself to write tests you did not think about
        4. Remember to refactor after each passing test
2. Allow the Add method to handle an unknown amount of numbers
3. Allow the Add method to handle new lines between numbers (instead of commas).
        1. the following input is ok:  “1\n2,3”  (will equal 6)
        2. the following input is NOT ok:  “1,\n” (not need to prove it - just clarifying)
4. Support different delimiters
        1. to change a delimiter, the beginning of the string will contain a separate line that looks like this:   “//[delimiter]\n[numbers…]” for example “//;\n1;2” should return three where the default delimiter is ‘;’ .
        2. the first line is optional. all existing scenarios should still be supported
5. Calling Add with a negative number will throw an exception “negatives not allowed” - and the negative that was passed.if there are multiple negatives, show all of them in the exception message. 

Continue if you can finish the steps so far in less than 30 minutes.

6. Numbers bigger than 1000 should be ignored, so adding 2 + 1001  = 2
7. Delimiters can be of any length with the following format:  “//[delimiter]\n” for example:
	“//[***]\n1***2***3” should return 6
8. Allow multiple delimiters like this:  “//[delim1][delim2]\n” for example “//[*][%]\n1*2%3” should return 6.
9. make sure you can also handle multiple delimiters with length longer than one char
