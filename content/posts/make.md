---
title : 'GNU Make'
date : 2023-12-17T14:45:30-06:00
draft : false
author : Hu
tags : ["UW-Madiosn", "CS400", "Makefile"]
categories: ["Courses"]
---

### **Makefile**  

GNU Make is a tool which controls the generation of executables and other non-source files of a program from the program's source files.

Make gets its knowledge of how to build your program from a file called the makefile, which lists each of the non-source files and how to compute it from other files. When you write a program, you should write a makefile for it, so that it is possible to use Make to build and install the program.  

A rule in the makefile tells Make how to execute a series of commands in order to build a target file from source files. It also specifies a list of dependencies of the target file. This list should include all files (whether source files or other targets) which are used as inputs to the commands in the rule.

Here is a simple exaple of how to create makefile and what it should looks like:  
In your terminal run: `vim Makefile` you can edit it by any editor you like, the Makefile template is something like this  

```.DEFAULT_GOAL := run
.PHONY: clean compile runBDTests

# Compile all Java files in the directory
compile:
	javac -cp .:../junit5.jar Backend.java BackendInterface.java BaseGraph.java DijkstraGraph.java GraphADT.java PlaceholderGraph.java PlaceholderMap.java ShortestPathInterface.java BackendDeveloperTests.java FrontendInterface.java MapADT.java

# Run backend developer tests
runBDTests: compile
	java -jar ../junit5.jar -cp . -c BackendDeveloperTests

# Main entrance of the application
run: compile
	java Backend

# Run frontend developer tests
runFDTests:
	javac -cp .:../junit5.jar *.java
	java -jar ../junit5.jar -cp . -c FrontendDeveloperTests

# Clean up compiled files
clean:
	rm -f *.class
```

          