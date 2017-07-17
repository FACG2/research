# research

Always document your learning - this helps you, your cohort, and future cohorts

# Test Coverage

### What is test coverage?
code coverage is a measure used to describe the degree to which the source code of a program is tested by a particular test suite.

### Why is test coverage useful?
In code coverage data gives us an important insight on how effective our tests are, what parts of our source code are thoroughly executed. You can also look at the code coverage report and find out specific areas of code which are not exercised by our tests.
**Code coverage reports should be used on a daily basis to:**
  1. see what percentage of tests actually test our code
  2. communicate with your testers and the QA team about the code bases which have very low test coverage
  3. improve the coverage by writing additional tests as more functionality is added.

### What are Istanbul and nyc?
  **Istanbul:** 
  is a code coverage analysis script you run when executing your unit tests,  it prints out nice html reports.
  **Nyc:**
    Istanbul command line interface (replacement for the old Istanbul bin )
  It uses Istanbul but works for sub processes.

### How do they improve code test?
##### Installation
```
npm install istanbul –save-dev
```
**to check if the installation worked**
```
node_modules/.bin/istanbul help
```
**For Example :**
We used the **FizzBuzz TDD** code in the TDD workshop
 **run the istanbul command to generate a coverage report:**
```
node ./node_modules/.bin/istanbul cover test.js
```
**ulternatively you can insert the line**
```
"coverage": "istanbul cover ./test.js"
```
into the scripts section of your package.json and run
```
npm run coverage
```
This will create a directory in your project called coverage where you will find the generated coverage reports.

**Istanbul gives us four code coverage metrics:**
**Statements:** How many of the statements in you code are executed.
**Branches:** Conditional statements create branches of code which may not be executed (e.g. if/else). This metric tells you how many of your branches have been executed.
**Functions:** The proportion of the functions you have defined which have been called.
**Lines:** The proportion of lines of code which have been executed.

 Done by: @Mahmoud-w, @Qamar, @Hana'a and @Kefah 
