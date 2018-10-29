# Java Makefile

This is a makefile for compiling java projects on Linux and Windows systems. It is designed to make projects, which are not complicated enough for a dedicated build system, but too complicated to want to try to compile by hand, portable and more easily sharable.

### Usage
1. Replace `jarfile.jar` with an appropriately named `.jar` file:
```
# The name of the jar file to create
JAR_FILE := jarfile.jar
```
2. Replace `main.Main` with the fully-qualified class name of the class containg the main function:
```
# The class containing `public static void main(String[] args)`
MAIN_CLASS := main.Main
```
Note: If the project depends on other projects or jar files, additional changes will have to be made.

### Rules
- `all` - Compiles the `.java` files and places the corresponding `.class` files in a `.jar` archive. This is the default rule.
- `run` - Compiles and runs the `.jar` file.
- `clean` - Removes the `.jar` file and `.class` files corresponding to the `.java` files.
- `cleanall` - Removes the `.jar` file and all `.class` files.

### How it works
The makefile will recursively find all `.java` files is a specified source directory (`src`). It then creates rules to compile those files and place them in a specified class folder (`bin`) while maintaining their file paths relative to the source directory. The default rule `all` depends on the compiled `.class` files and will create a runnable `.jar` archive.
