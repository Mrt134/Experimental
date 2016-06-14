.. _competitive analysis:

Fuzz Testing
============

term
why is difficult
optimize fuzz

terminology
-----------

Non-Functional: tests do not relate to functionality - a successful test generates a core file
Fuzz: random data
Monkey: random actions
Exploratory: unscripted, iterative test design/implementation/execution - testing frameworks need to allow for experimentation

Fuzzing Structure Data
----------------------

Interfaces

Protocols - you can ignore the data type
sometimes there is an advantage to really examine the data and determine specific functions to fuzz

Classic tests
Random command generator
File system exerciser
Ballista OS robustness test suite - fuzz testing of one single Function
fuzz tests become less useful over time, investment is required to write a test that can be reused for years
There is a tendency to have too much complexity in fuzz testing, which makes it hard for a human to review the data

programmers are taught to reduce complexity, but testers may need to increase complexity for testing improvements

What is being fuzzed?
 regular execution paths
 random execution
 ordering of kernel calls
 objects used by kernel calls
 actual set of kernel calls
 
lifecycle of testing
write spaghetti code and test
instead write an API between the tests and execution
try splitting fuzz test rameworks in half - fuzz gen - () - execution
when you have a data set, it can now be changed
using a competitive model for testing finds the most critical errors one at a time
scaling up allows for more competitions to find more bugs simultaneously

hidden objects can be a source of panics that fuzz testing can miss
same with short v. long sym links
fuzz testing against operating systems can be boring when no bugs are found
once a bug is identified, it becomes valuable to create additional tests to reproduce the bug more quickly (competition method works well)
competitions can narrow the bug down most of the way, but now the competition method can be applied as operation vs operation, narrowing down to just the essential operations that produce the panic. a kernel panic bug can be reduced in this way from 8hrs to reproduce to 30 seconds to reproduce.
testing the kernel in an opensource program should be using an existing execution framework. another improvement might be to automate the generation of operations for testing.

there are some options to improve automated testing via moving out of production kernels or integrating dtrace into the testing process
there is a tool called delta which does some of the same testing in a more automated manner.
