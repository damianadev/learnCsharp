# LearnC#

**!!!WARNING This documentation is not yet finished and may contain mistakes or missing information. WARNING!!!**

## Useful Links

[draw.io](https://www.drawio.com/) - Use this website to draw data schemas before writing them.
[Microsoft .NET](https://learn.microsoft.com/en-us/dotnet/) - If you cannot find what you are looking for in my documentation, check the official Microsoft documentation.

## Table of Contents

- [Foundational Skills](#foundational-skills)
  - [Syntax Basics](#syntax-basics)
  - [Outputs](#outputs)
  - [Inputs](#inputs)
  - [Variables](#variables)
  - [Data Types](#data-types)
  - [Operators](#operators)
  - [Conditions & Loops](#conditions--loops)
  - [Methods](#methods)
- [Advanced Skills](#advanced-skills)
  - [Entity Framework Core (EF Core)](#entity-framework-core-ef-core)
  - [ORM (Object-Relational Mapping)](#orm-object-relational-mapping)
  - [LINQ](#linq)
  - [MediatR](#mediatr)
- [Coming soon](#coming-soon-1)
  - [Migrations](#migrations)
  - [CRUD](#crud)
  - [HTTP Methods (GET, POST, PUT, PATCH, DELETE)](#http-methods-get-post-put-patch-delete)
  - [DTO](#dto)
  - [Paging (Pagination)](#paging-pagination)

---

# Foundational Skills

**Foundational skills for getting started with C#.**

## Syntax Basics

**C# syntax is very similar to JavaScript, but the languages have different rules and features.**

- `using System;` — Makes types from the `System` namespace available by their short names.
- `namespace` — Organizes related classes, structs, interfaces, and other types.
- `class` — A blueprint for creating objects. It can contain data (fields and properties) and methods.

- Blank lines organize code and make it more readable.
- Curly braces `{ }` mark the beginning and the end of a code block.
- Most C# statements end with a semicolon `;`.
- C# is case-sensitive. For example, `myClass` and `MyClass` are different identifiers.

> **Note:** Modern C# projects can use top-level statements, meaning you do not always need to explicitly create a class or a `Main` method.

## Outputs

**1. Console.WriteLine() method**

- `Console.WriteLine("Hello World!");` — Outputs "Hello World!" and moves to a new line.

**2. Console.Write() method**

- `Console.Write("Hello World!");`
- `Console.Write("I am learning C#");`

These statements output all text on the same line because `Console.Write()` does not automatically move to a new line.

**3. Console.WriteLine() with variables**

You can output the values of variables using `Console.WriteLine()`.

**Example**

```csharp
string name = "John";
int age = 20;

Console.WriteLine(name);
Console.WriteLine(age);
```

**Output**

```
John
20
```

**4. String interpolation**

String interpolation allows you to insert variable values directly into a string using `$` and curly braces `{ }`.

**Example**

```csharp
string name = "John";
int age = 20;

Console.WriteLine($"My name is {name} and I am {age} years old.");
```

**Output**

```
My name is John and I am 20 years old.
```

## Inputs

### Console.ReadLine() method

- `Console.ReadLine()` — Reads a line of text entered by the user in the console.
- It returns the input as a `string`.

**Example**

```csharp
Console.WriteLine("Enter your name:");

string name = Console.ReadLine();

Console.WriteLine($"Hello, {name}!");
```

**Example output**

```
Enter your name:
John
Hello, John!
```

### Converting input to other data types

Since `Console.ReadLine()` returns a string, you need to convert the input when you want to work with numbers or other data types.

**1. Convert.ToInt32()**

Converts a value to a 32-bit integer (`int`).

```csharp
Console.WriteLine("Enter your age:");

int age = Convert.ToInt32(Console.ReadLine());

Console.WriteLine($"You are {age} years old.");
```

**2. Convert.ToDouble()**

Converts a value to a `double`.

```csharp
Console.WriteLine("Enter a number:");

double number = Convert.ToDouble(Console.ReadLine());

Console.WriteLine($"Your number is {number}");
```

**3. int.Parse()**

Converts a string into an integer.

```csharp
Console.WriteLine("Enter a number:");

int number = int.Parse(Console.ReadLine());

Console.WriteLine($"Your number is {number}");
```

**Important:**

- `Convert.ToInt32()` and `int.Parse()` can throw an exception if the input cannot be converted to an integer.
- `double.Parse()` can throw an exception if the input is not a valid number.
- `int.TryParse()` is a safer alternative because it checks whether the conversion succeeds without throwing an exception for invalid input.

**4. int.TryParse()**

Attempts to convert a string into an integer and returns `true` if successful or `false` if the conversion fails.

```csharp
Console.WriteLine("Enter your age:");

string input = Console.ReadLine();

if (int.TryParse(input, out int age))
{
    Console.WriteLine($"You are {age} years old.");
}
else
{
    Console.WriteLine("Invalid input. Please enter a number.");
}
```

## Variables

- `int` — Stores whole numbers (integers), without decimals, such as `123` or `-123`.
- `double` — Stores floating-point numbers, with decimals, such as `19.99` or `-19.99`.
- `float` — Stores floating-point numbers with less precision than `double`.
- `decimal` — Stores high-precision decimal numbers, commonly used for financial calculations.
- `char` — Stores a single UTF-16 code unit, such as `'a'` or `'B'`. Char values are surrounded by single quotes.
- `string` — Stores text, such as `"Hello World"`. String values are surrounded by double quotes.
- `bool` — Stores one of two values: `true` or `false`.

**How to create variables?**

```csharp
type variableName = value;
```

**Examples**

```csharp
int myNum = 5;
double myDoubleNum = 5.99;
float myFloat = 5.75F;
decimal myPrice = 19.99m;
char myLetter = 'D';
bool myBool = true;
string myText = "Hello";
```

- Data stored in variables can be changed, as long as the new value has a compatible data type.

### Const

- `const` — Stores a value that cannot be changed after declaration. A const variable must be initialized when it is declared.

**Example**

```csharp
const int myNum = 15;

// myNum = 20; // Error: a constant cannot be changed

Console.Write(myNum); // Output: 15
```

### Var

- `var` — Automatically determines the data type of a local variable based on its assigned value.
- The data type is determined at compile time and cannot be changed later.

**Example**

```csharp
var age = 20;        // int
var name = "John"; // string
var price = 9.99;    // double
```

**Example**

```csharp
var age = 20;

age = 25;          // OK
// age = "Hello";  // Error: age is an int
```

## Data Types

| Type | Size | Description |
|---|---|---|
| `byte` | 1 byte | Stores whole numbers from 0 to 255 |
| `short` | 2 bytes | Stores whole numbers from -32,768 to 32,767 |
| `int` | 4 bytes | Stores whole numbers from -2,147,483,648 to 2,147,483,647 |
| `long` | 8 bytes | Stores whole numbers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `float` | 4 bytes | Stores floating-point numbers with about 6–9 significant decimal digits |
| `double` | 8 bytes | Stores floating-point numbers with about 15–17 significant decimal digits |
| `decimal` | 16 bytes | Stores high-precision decimal numbers with about 28–29 significant decimal digits |
| `bool` | Not fixed by the C# language | Stores `true` or `false` values |
| `char` | 2 bytes | Stores one UTF-16 code unit |
| `string` | Variable | Stores a sequence of characters |

**Examples**

```csharp
int myInt = 100000;
long myLong = 15000000000L;
float myFloat = 5.75F;
double myDouble = 19.99D;
decimal myDecimal = 19.99m;

bool isCSharpFun = true;
bool isFishTasty = false;

Console.WriteLine(isCSharpFun); // Outputs True
Console.WriteLine(isFishTasty); // Outputs False

char myGrade = 'B';
string greeting = "Hello World";
```

**Numeric suffixes**

- `L` — long
- `F` — float
- `D` — double (usually optional)
- `M` — decimal

> **Note:** A string is immutable, meaning its contents cannot be changed after it has been created. Operations that appear to modify a string create a new string.

## Operators

**Operators are used to perform operations on variables and values.**

### Arithmetic Operators

| Operator | Name | Description | Example |
|---|---|---|---|
| `+` | Addition | Adds two values | `x + y` |
| `-` | Subtraction | Subtracts one value from another | `x - y` |
| `*` | Multiplication | Multiplies two values | `x * y` |
| `/` | Division | Divides one value by another | `x / y` |
| `%` | Remainder | Returns the remainder after division | `x % y` |
| `++` | Increment | Increases a variable by 1 | `x++` |
| `--` | Decrement | Decreases a variable by 1 | `x--` |

**Examples**

```csharp
int sum1 = 100 + 50;    // 150
int sum2 = sum1 + 250;  // 400
int sum3 = sum2 + sum2; // 800
```

> **Note:** When both operands of division are integers, C# performs integer division and discards the fractional part.

```csharp
Console.WriteLine(5 / 2);   // Output: 2
Console.WriteLine(5.0 / 2); // Output: 2.5
```

### Assignment Operators

| Operator | Example | Same As |
|---|---|---|
| `=` | `x = 5` | Assigns 5 to x |
| `+=` | `x += 3` | `x = x + 3` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 3` | `x = x * 3` |
| `/=` | `x /= 3` | `x = x / 3` |
| `%=` | `x %= 3` | `x = x % 3` |
| `&=` | `x &= 3` | `x = x & 3` |
| `\|=` | `x \|= 3` | `x = x \| 3` |
| `^=` | `x ^= 3` | `x = x ^ 3` |
| `>>=` | `x >>= 3` | `x = x >> 3` |
| `<<=` | `x <<= 3` | `x = x << 3` |

**Example**

```csharp
int x = 10;

x += 5; // x = 15

Console.WriteLine(x); // Output: 15
```

### Comparison Operators

| Operator | Name | Example |
|---|---|---|
| `==` | Equal to | `x == y` |
| `!=` | Not equal | `x != y` |
| `>` | Greater than | `x > y` |
| `<` | Less than | `x < y` |
| `>=` | Greater than or equal to | `x >= y` |
| `<=` | Less than or equal to | `x <= y` |

**Examples**

```csharp
int x = 5;
int y = 3;

Console.WriteLine(x > y); // Outputs True
```

### Logical Operators

| Operator | Name | Description | Example |
|---|---|---|---|
| `&&` | Logical AND | Returns true if both conditions are true | `x < 5 && x < 10` |
| `\|\|` | Logical OR | Returns true if at least one condition is true | `x < 5 \|\| x < 4` |
| `!` | Logical NOT | Reverses the Boolean result | `!(x < 5 && x < 10)` |

**Important:**

- `&&` — Does not evaluate the second condition if the first condition is false.
- `||` — Does not evaluate the second condition if the first condition is true.

**Examples**

```csharp
int x = 5;
int y = 3;

Console.WriteLine(x < 10 && y > 5); // False
Console.WriteLine(x > 10 || y > 5); // False
Console.WriteLine(!(x < 10));       // False
```

## Conditions & Loops

### if, else if & else

**Syntax**

```csharp
if (firstCondition)
{
    // Runs if firstCondition is true.
}
else if (secondCondition)
{
    // Runs if firstCondition is false and secondCondition is true.
}
else
{
    // Runs if neither condition is true.
}
```

**Example**

```csharp
int time = 22;

if (time < 10)
{
    Console.WriteLine("Good morning.");
}
else if (time < 20)
{
    Console.WriteLine("Good day.");
}
else
{
    Console.WriteLine("Good evening.");
}

// Outputs "Good evening."
```

### while loop & do/while loop

**while loop**

```csharp
while (condition)
{
    // Code block to be executed.
}
```

**Example**

```csharp
int i = 0;

while (i < 5)
{
    Console.WriteLine(i);
    i++;
}
```

- The condition is checked before each iteration.
- If the condition is false at the beginning, the loop will not execute.

**do/while loop**

```csharp
do
{
    // Code block to be executed.
}
while (condition);
```

**Example**

```csharp
int i = 0;

do
{
    Console.WriteLine(i);
    i++;
}
while (i < 5);
```

- The condition is checked after the code block executes.
- The code block always executes at least once.

### for loop & foreach loop

**for loop**

```csharp
for (initialization; condition; iterator)
{
    // Code block to be executed.
}
```

**Example**

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

- Initialization — Runs once before the loop starts.
- Condition — Checked before each iteration.
- Iterator — Runs after each iteration.

**foreach loop**

```csharp
foreach (type variableName in collection)
{
    // Code block to be executed.
}
```

**Example**

```csharp
string[] cars = { "Volvo", "BMW", "Ford", "Mazda" };

foreach (string car in cars)
{
    Console.WriteLine(car);
}
```

- The foreach loop iterates through each element in a collection.
- The variable `car` represents the current element.

### break & continue

**break**

The `break` statement immediately terminates the nearest enclosing loop or switch statement.

**Example**

```csharp
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

Output: `0, 1, 2, 3`

**continue**

The `continue` statement skips the rest of the current iteration and moves to the next iteration of the loop.

**Example**

```csharp
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

This example skips 4 and prints the other values from 0 to 9.

## Methods

A **method** is a named block of code that performs a specific task. Methods can receive input through parameters and return a value.

**Example**

```csharp
static int Add(int a, int b)
{
    return a + b;
}
```

**Calling the method**

```csharp
int result = Add(5, 3);

Console.WriteLine(result); // Output: 8
```

- `int` — Return type.
- `Add` — Method name.
- `a` and `b` — Parameters.
- `return` — Sends a value back to the code that called the method.

**void method**

A method with `void` as its return type does not return a value.

```csharp
static void SayHello()
{
    Console.WriteLine("Hello!");
}
```

---

# Advanced Skills

**More advanced concepts used when building larger applications.**

## Entity Framework Core (EF Core)

- Entity Framework Core (EF Core) is an ORM (Object-Relational Mapper) for .NET that allows developers to interact with relational databases using C# objects and LINQ instead of writing SQL for every database operation.
- EF Core maps C# classes and their properties to database tables and columns according to its conventions and configuration.

**A simple example of the mapping**

| C# concept | Database equivalent |
|---|---|
| Entity class | Table |
| Entity object | Row |
| Property | Column |

This is a basic analogy. Actual database mappings can be more complex.

**Example**

```csharp
public class Customer
{
    public int Id { get; set; }

    public string Name { get; set; } = string.Empty;

    public string Email { get; set; } = string.Empty;
}
```

- EF Core can map this class to a Customers table.
- Declaring the class alone does not automatically create the table in an existing database.
- You normally configure the entity in a DbContext, create a migration, and apply that migration to the database.

**Important EF Core terms**

- **Entity** — A C# object that EF Core maps to database data.
- **DbContext** — Represents a session with the database and coordinates querying and saving changes.
- **DbSet\<TEntity\>** — Represents a set of entities that can be queried and saved.
- **Migration** — A set of changes used to keep the database schema synchronized with the data model.
- **SaveChanges() / SaveChangesAsync()** — Saves tracked changes to the database.

## ORM (Object-Relational Mapping)

- ORM (Object-Relational Mapping) is a technique that allows developers to work with relational databases using objects and classes instead of writing SQL for every database operation.
- An ORM is a tool or framework that implements this technique. EF Core is an example of an ORM for .NET.

**Example using SQL**

```sql
SELECT * FROM Customers;
```

**Similar query using C# and EF Core**

```csharp
var customers = await _context.Customers.ToListAsync();
```

- `_context` is an instance of a class that inherits from DbContext.
- `Customers` is a `DbSet<Customer>` property.
- `ToListAsync()` executes the query asynchronously and returns the results as a list.
- `await` waits for the asynchronous operation to finish.

**Required namespace**

```csharp
using Microsoft.EntityFrameworkCore;
```

- EF Core translates supported LINQ query expressions into SQL for the configured database provider.
- The generated SQL depends on the database provider and the query.

## LINQ

**LINQ (Language Integrated Query)** is a set of C# language features and APIs that allows developers to query data from collections and other data sources.

**Common LINQ methods**

- `Where()` — Filters elements based on a condition.
- `Select()` — Selects or transforms elements.
- `OrderBy()` — Sorts elements in ascending order.
- `OrderByDescending()` — Sorts elements in descending order.
- `FirstOrDefault()` — Returns the first matching element or the default value if no element is found.
- `ToList()` — Executes a query and creates a list from its results.

**Example**

```csharp
int[] numbers = { 1, 2, 3, 4, 5, 6 };

var evenNumbers = numbers
    .Where(number => number % 2 == 0)
    .ToList();

Console.WriteLine(string.Join(", ", evenNumbers)); // Output: 2, 4, 6
```

- LINQ can be used with in-memory collections and database queries.
- When LINQ is used with EF Core, supported query expressions are translated into SQL by the database provider.
- LINQ itself is not SQL. It is a way to express queries in C#.

## MediatR

**MediatR** is a .NET library that implements the mediator pattern. It helps different parts of an application communicate by sending requests or notifications through a mediator instead of calling each other directly.

**Common concepts**

- **Request** — A message that asks the application to perform an operation and may return a response.
- **Handler** — A class that processes a request.
- **Notification** — A message that can be handled by one or more notification handlers.
- **Mediator** — The component that sends requests or publishes notifications to their handlers.

<!-- -->

- MediatR is often used in applications that follow the CQRS pattern.
- CQRS separates operations that change data (commands) from operations that read data (queries).
- MediatR does not replace EF Core or create a database. It helps organize communication between application components.

# Coming Soon...

## Migrations
## CRUD
## HTTP Methods (GET, POST, PUT, PATCH, DELETE)
## DTO 
## Paging (Pagination)