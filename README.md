# Stipula Prototype

Stipula is a domain specific language that may assist legal practitioners in programming legal contracts through specific patterns.
In this repository, we uploaded the prototype and some examples.

## Description

The prototype is a Java application. The development has taken three months and ~3000 lines of Java code. 
We have committed to the ANTLR tool.

## Getting Started

### Dependencies

* The prototype requires a Java version > 8.
* Maven 3.x (for the standard project layout).

### Installation

There are two possibilities:
* It is possible to install the source code with the grammar and generate the parser
* It is possible to download and run the jar of the prototype


#### How to install the source code

##### Requirements:
* Java > 8
* ANTLR > 4.4

##### Instructions:
* Download the zip
* Build with Maven (this generates the parser, visitor, and listener from the grammar)
* The project uses the standard Maven layout:
  * `src/main/java` for sources
  * `src/main/resources` for resources
  * `src/main/antlr4` for the grammar

To build:
```
mvn -q clean package
```

#### How to run the jar

* After downloading the zip, go to the correct folder (./Stipula Executable)
* To run the prototype type the following code
```
java -jar Stipula-LAN.jar name_of_the_example.stipula
```
* If you build with Maven, the jar is created in `target/`:
```
java -jar target/stipula-0.1.0-SNAPSHOT.jar name_of_the_example.stipula
```
 
### Execution

* When the prototype starts, it displays the type inference 
* Then the agreement starts and displays a unique code for each party of the contract (see example below)
```
--------------------
Lender ef6h4
Borrower MHWBs
Authority gxhZZ
--------------------
```
* The prototype asks the user to insert these codes and the values for some variables
* Then it shows which functions can start, for instance:
```
# Please, choose which function should run: 
	Lender.offer(Type3 x)[]
```
* The user must call the desired function by inserting the corresponding party's code and the values for the formal parameters
* For instance, if the lender wants to call the function offer with x=10:
```
	ef6h4.offer(10)[]
```
* Then the prototype executes the body of the chosen function and the execution continues
