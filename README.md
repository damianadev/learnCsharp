# LearnC#

***https://www.drawio.com/*** --- Use this website to draw data schemas before write them.


# Foundational Skills

**Foundational skills for getting started with C#**

## Syntax Basics

**C#'s syntax is very similar with JS**

- using System --- System means that I can use classes from "System" namespace.
- namespace --- Namespace is used to organize code, it creates "containers" for storing classes and other namespaces.
- class --- class is a container that stores every data and methods, every line that is written in C# needs to be in class.


- Blank lines are used to organize code and make code more readable.
- The curly brackets {} are marking the start and the end of a block of code.
- Every C# statement ends with semicolon ; .
- Every letter in the name of the namespace or class is important, so for example "myclass" and "MyClass" aree different things.


## Outputs

1. Console.WriteLine method
- `Console.WriteLine("Hello World!")` --- This method will output "Hello World!" in a new line.

2. Console.Write method
- `Console.Write("Hello World!");`
- `Console.Write("I am learning C#");`
- `Console.Write("I like C#");` --- These methods will output all text in the same line.


## Variables 

- int       ---      stores integers (whole numbers), without decimals, such as 123 or -123
- double    ---      stores floating point numbers, with decimals, such as 19.99 or -19.99
- char      ---      stores single characters, such as 'a' or 'B'. Char values are surrounded by single quotes
- string    ---      stores text, such as "Hello World". String values are surrounded by double quotes
- bool      ---      stores values with two states: true or false


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

**Constants**

```
const int myNum = 15;
myNum = 20; // error
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


## Operators

**Operators are used to perform operations on variables and values.**


### Arithmetic Operators

| Operator | Name           | Description                     | Example |
|----------|----------------|---------------------------------|---------|
| `+`      | Addition       | Adds together two values        | `x + y` |
| `-`      | Subtraction    | Subtracts one value from another| `x - y` |
| `*`      | Multiplication | Multiplies two values           | `x * y` |
| `/`      | Division       | Divides one value by another    | `x / y` |
| `%`      | Modulus        | Returns the division remainder  | `x % y` |
| `++`     | Increment      | Increases the value of a variable by 1 | `x++` |
| `--`     | Decrement      | Decreases the value of a variable by 1 | `x--` |

**Examples**

```
int sum1 = 100 + 50;        // 150 (100 + 50)
int sum2 = sum1 + 250;      // 400 (150 + 250)
int sum3 = sum2 + sum2;     // 800 (400 + 400)
```
___


### Assigment Operators

| Operator | Example | Same As |
| :------- | :------ | :------ |
| `=`      | `x = 5`   | `x = 5`      |
| `+=`     | `x += 3`  | `x = x + 3`  |
| `-=`     | `x -= 3`  | `x = x - 3`  |
| `*=`     | `x *= 3`  | `x = x * 3`  |
| `/=`     | `x /= 3`  | `x = x / 3`  |
| `%=`     | `x %= 3`  | `x = x % 3`  |
| `&=`     | `x &= 3`  | `x = x & 3`  |
| `I=`     | `x I= 3`  | `x = x I 3`  |
| `^=`     | `x ^= 3`  | `x = x ^ 3`  |
| `>>=`    | `x >>= 3` | `x = x >> 3` |
| `<<=`    | `x <<= 3` | `x = x << 3` |

**Examples**

```
int x = 10;
x += 5;     // Answer x = 15
```
___


### Comparison Operators

| Operator | Name                     | Example |
| :------- | :----------------------- | :------ |
| `==`     | Equal to                 | `x == y` |
| `!=`     | Not equal                | `x != y` |
| `>`      | Greater than             | `x > y` |
| `<`      | Less than                | `x < y` |
| `>=`     | Greater than or equal to | `x >= y` |
| `<=`     | Less than or equal to    | `x <= y` |

**Examples**

```
int x = 5;
int y = 3;
Console.WriteLine(x > y); // returns True because 5 is greater than 3
```
___


### Logical Operators

| Operator | Name        | Description                                             | Example |
| :------- | :---------- | :------------------------------------------------------ | :------ |
| `&&`     | Logical and | Returns True if both statements are true                | `x < 5 && x < 10` |
| `II`     | Logical or  | Returns True if one of the statements is true           | `x < 5 II x < 4` |
| `!`      | Logical not | Reverse the result, returns False if the result is true | `!(x < 5 && x < 10)` |

**Examples**

```
Console.WriteLine(x < 10 && y > 5); // True 
Console.WriteLine(x > 10 || y > 5); // True 
Console.WriteLine(!(x < 10)); // False
```


## Functions


### if & else if & else syntax

```
if( first_condition )
{
    // What happens when first_condition is true?
} 
else if ( second_condition )
{
    // What happens when second_condition is true?
}
else
{
    // What happens if first and second conditions are false?
}
```


### while loop & do/while loop syntax

**while loop**

```
while (condition) 
{
  // code block to be executed
}
```

___

**do/while loop**

```
do 
{
  // code block to be executed
}
while (condition);
```


### break & continue

**break**

The `break` statement terminates the loop when a specified condition occurs.

**Example in while loop**

```
int i = 0;
while (i < 10) 
{
  Console.WriteLine(i);
  i++;
  if (i == 4) 
  {
    break;
  }
}
```

___

**continue**

The `continue` statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.

**Example in while loop**

```
int i = 0;
while (i < 10) 
{
  if (i == 4) 
  {
    i++;
    continue;
  }
  Console.WriteLine(i);
  i++;
}
```


# Advanced Skills

**Advanced Skills in writing more complex code**

## EnityFramework Core


## MediatR
