# CS182 Project Option 1: Classical Software Testing with JQF
## Requirements
In order to use JQF and its edited versions present here, **JDK/OpenJDK 21**\* and **Maven** are required.
The commands listed in this guide are specific for usage on Linux, though may also work on other UNIX-based systems.

\* May work with lower versions as well, but they are untested.
## Setting Up JQF
To use a given version of JQF, it must first be built. This can be done by executing the setup script contained in each folder: `.JQF/setup.sh`.

## Compiling the PUT
The provided sample program, `SimpleTest.java`, can be compiled using the command: `javac -cp .:$(JQF/scripts/classpath.sh) SimpleTest.java`. This will generate `SimpleTest.class`.

## Fuzzing the PUT with standard JQF
JQF can be used to fuzz the program's bytecode with the following command: `JQF/bin/jqf-random SimpleTest testSimpleTest 10`
This command can be used on other programs with the format `JQF/bin/jqf-random TEST_CLASS TEST_METHOD MAX_TRIALS`.

## Fuzzing with Addtional Coverage Information Printed
`JQF-2` and `JQF-3` contain edited versions of JQF that print additional coverage information when fuzzing with `jqf-random`. 

JQF-2 will print branch decisions on all Branch Events, with `0` representing a false branch and `1` representing a true branch.
JQF-2's fuzzing can be performed on the PUT with the command: `JQF-2/bin/jqf-random SimpleTest testSimpleTest 10`.

JQF-3 will print information about all events on all threads, while also only providing the PUT with an input of 200.
JQF-3's fuzzing can be performed on the PUT with the command: `JQF-3/bin/jqf-random SimpleTest testSimpleTest 10`.
