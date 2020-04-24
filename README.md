# Java Makefile
[![GitHub license](https://img.shields.io/github/license/AlexandreLadriere/Java-Makefile.svg)](https://github.com/AlexandreLadriere/Java-Makefile/blob/master/LICENSE)

The [make.sh] script is a basic _Makefile_ shell script for Java projects which can be useful if you are developing without an IDE and/or if you want something really fast to build your project.

__You have to place this script at the root of your Java project, and run it from this root.__

## How to use
### Initializing variables
First, you will have to modify some variables in the [make.sh] script in order to adapt it to your project.
You have to set up all the variables in the ``PATHS`` section (the ``TEST_PATH`` variable is optional and can be left empty).
```shell script
########## PATHS ##########
# Folder containing all src files
# ex: SRC_PATH="src/"
SRC_PATH=""
# Folder containing resources (must be in the SRC_PATH folder)
# ex: RESOURCES="main/resources/"
RESOURCES=""
# Folder where all .class files will be created
# ex: OUT_PATH="out/"
OUT_PATH=""
# Folder in which the javadoc will be created
# ex: DOC_PATH="doc/"
DOC_PATH=""
# Folder containing JUnit tests for instance. This path must have the following format: ./path*
# ex: TEST_PATH="./test*" (test/ is in src/ like main/)
TEST_PATH=""
```
Then, you also have to set up the variables in the ``USER VARIABLES`` section (the ``EXCLUDE`` array is optional and can be left empty).
```shell script
########## USER VARIABLE ##########
# String array of files that you want to exclude from the compilation. You MUST give the full relative path of the files starting from the src/ subfolder
# ex: declare -a EXCLUDE=(
#       "./main/java/fr/alexandreladriere/shortestpath/gui/Case.java"
#       "./main/java/fr/alexandreladriere/shortestpath/gui/Gui.java"
#     )
declare -a EXCLUDE=()
# Main class name, without .jave extension and with full relative path starting from the src/ subfolder
# ex: MAIN="main/java/fr/alexandreladriere/shortestpath/ShortestPath"
MAIN=""
```   

All examples given in the script were based on a project having the following structure:
```
├── make.sh
├── src
│    ├── main
│    │    ├── java
│    │    │    └── ... (packages and .java files)
│    │    └── resources
│    ├── test
│    │    ├── java
│    │    │    └── ... (packages and .java files)
└──  └──  └── resources
```

### Command line uses
#### Build all .class files
```shell script
$ sh make.sh build
```

#### Run the app
```shell script
$ sh make.sh run # it will build the app if it is not done yet
```

#### Build JAR file
```shell script
$ sh make.sh build-jar # it will build the app if it is not done yet
```
_Windows users can simply double-click on the [make.sh] to build the jar_

#### Create Javadoc
```shell script
$ sh make.sh doc
```

#### Clean
```shell script
$ sh make.sh clean
```

#### Help
```shell script
$ sh make.sh help
```

## License
This project is licensed under the MIT License - see the [LICENSE] file for details.

## Contributing
Contributions are welcome :smile:

### Pull requests
Just a few guidelines:
-   Write clean code with appropriate comments and add suitable error handling.
-   Test the application and make sure no bugs/ issues come up.
-   Open a pull request, and I will be happy to acknowledge your contribution after some checking from my side.

### Issues
If you find any bugs/issues, raise an issue.

  [LICENSE]: <LICENSE>
  [make.sh]: <make.sh>