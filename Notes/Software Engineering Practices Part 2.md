Testing
---------
Testing your code is essential before deployment. It helps you catch errors and faulty conclusions before they make any major impact. Today, employers are looking for data scientists with the skills to properly prepare their code for an industry setting, which includes testing their code.

Testing And Data Science
---------------------------
Problems that could occur in data science aren’t always easily detectable; you might have values being encoded incorrectly, features being used inappropriately, or unexpected data breaking assumptions.
To catch these errors, you have to check for the quality and accuracy of your analysis in addition to the quality of your code. Proper testing is necessary to avoid unexpected surprises and have confidence in your results.
Test-driven development (TDD): A development process in which you write tests for tasks before you even write the code to implement those tasks.
Unit test: A type of test that covers a “unit” of code—usually a single function—independently from the rest of the program.
Resources
Four Ways Data Science Goes Wrong and How Test-Driven Data Analysis Can Help: Blog Post
Ned Batchelder: Getting Started Testing: Slide Deck and Presentation Video

Unit tests
------------
We want to test our functions in a way that is repeatable and automated. Ideally, we'd run a test program that runs all our unit tests and cleanly lets us know which ones failed and which ones succeeded. Fortunately, there are great tools available in Python that we can use to create effective unit tests!

Unit test advantages and disadvantages
The advantage of unit tests is that they are isolated from the rest of your program, and thus, no dependencies are involved. They don't require access to databases, APIs, or other external sources of information. However, passing unit tests isn’t always enough to prove that our program is working successfully. To show that all the parts of our program work with each other properly, communicating and transferring data between them correctly, we use integration tests. In this lesson, we'll focus on unit tests; however, when you start building larger programs, you will want to use integration tests as well.

To learn more about integration testing and how integration tests relate to unit tests, see Integration Testing. That article contains other very useful links as well.

Unit Testing Tools
=====================
To install pytest, run pip install -U pytest in your terminal. You can see more information on getting started here.

Create a test file starting with test_.
Define unit test functions that start with test_ inside the test file.
Enter pytest into your terminal in the directory of your test file and it detects these tests for you.
test_ is the default; if you wish to change this, you can learn how in this pytest configuration.

In the test output, periods represent successful unit tests and Fs represent failed unit tests. Since all you see is which test functions failed, it's wise to have only one assert statement per test. Otherwise, you won't know exactly how many tests failed or which tests failed.

Your test won't be stopped by failed assert statements, but it will stop if you have syntax errors.


Test-driven development and data science
============================================

Test-driven development: Writing tests before you write the code that’s being tested. Your test fails at first, and you know you’ve finished implementing a task when the test passes.
Tests can check for different scenarios and edge cases before you even start to write your function. When start implementing your function, you can run the test to get immediate feedback on whether it works or not as you tweak your function.
When refactoring or adding to your code, tests help you rest assured that the rest of your code didn't break while you were making those changes. Tests also helps ensure that your function behavior is repeatable, regardless of external parameters such as hardware and time.
Test-driven development for data science is relatively new and is experiencing a lot of experimentation and breakthroughs. You can learn more about it by exploring the following resources.

Data Science TDD
TDD for Data Science
TDD is Essential for Good Data Science Here's Why
Testing Your Code (general python TDD)

Logging
=========
Logging is valuable for understanding the events that occur while running your program. For example, if you run your model overnight and the results the following morning are not what you expect, log messages can help you understand more about the context in those results occurred. Let's learn about the qualities that make a log message effective.

