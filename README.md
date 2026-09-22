# This is a tutorial for C#, I will write here what I learned so far in C#


## Syntax Basics

- using System --- System means that I can use classes from "System" namespace.
- namespace --- Namespace is used to organize code, it creates "containers" for storing classes and other namespaces.
- class --- class is a container that stores every data and methods, every line that is written in C# needs to be in class.


- Blank lines are used to organize code and make code more readable.
- The curly brackets {} are marking the start and the end of a block of code.
- Every C# statement ends with semicolon ; like in JS.
- Every letter in the name of the namespace or class is important, so for example "myclass" and "MyClass" aree different things.


## Outputs

1. 
- `Console.WriteLine("Hello World!")` --- This method will output "Hello World!" in a new line.

2. 
- `Console.Write("Hello World!");`
- `Console.Write("I am learning C#");`
- `Console.Write("I like C#");` --- These methods will output all text in the same line.


## Variables 

- int       ---      stores integers (whole numbers), without decimals, such as 123 or -123
- double    ---      stores floating point numbers, with decimals, such as 19.99 or -19.99
- char      ---      stores single characters, such as 'a' or 'B'. Char values are surrounded by single quotes
- string    ---      stores text, such as "Hello World". String values are surrounded by double quotes
- bool      ---      stores values with two states: true or false

___

**How to create variables?**

`type variableName = value;`


**Examples**

```
int myNum = 5;
double myDoubleNum = 5.99D;
char myLetter = 'D';
bool myBool = true;
string myText = "Hello";
```


## Data Types

| Type   | Size              | Description |
|--------|-------------------|-------------|
| int    | 4 bytes           | Stores whole numbers from -2,147,483,648 to 2,147,483,647 |
| long   | 8 bytes           | Stores whole numbers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| float  | 4 bytes           | Stores fractional numbers. Sufficient for storing 6 to 7 decimal digits |
| double | 8 bytes           | Stores fractional numbers. Sufficient for storing 15 decimal digits |
| bool   | 1 byte            | Stores true or false values |
| char   | 2 bytes            | Stores a single character/letter, surrounded by single quotes |
| string | 2 bytes per char   | Stores a sequence of characters, surrounded by double quotes |

**Examples**

```
int myNum = 100000;
long myNum = 15000000000L;
float myNum = 5.75F;
double myNum = 19.99D;

bool isCSharpFun = true;
bool isFishTasty = false;
Console.WriteLine(isCSharpFun);   // Outputs True
Console.WriteLine(isFishTasty);   // Outputs False

char myGrade = 'B';
string greeting = "Hello World";
```
