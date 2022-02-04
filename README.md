# C-Sharp-Notes

<br>

# Index<br>

[Terminology](#Terminology)<br>
[Main()](#Main)<br>
[DataTypes](#DataTypes)<br>
[Operators](#Operators)<br>
[Params Keyword](#Params-Keyword)<br>
[Properties](#Properties)<br>
[Access Modifiers](#Access-Modifiers)<br>
[Inheritance](#Inheritance)<br>



[Order Of Items In Classes](#Order-Of-Items-In-Classes)<br>




# Terminology

**Кодовый файл (.cs csharp code file)** — это один из файлов на языке C#.

**Проект (project)** — это совокупность кодовых файлов, которые могут быть скомпилированы в сборку: программу или библиотеку.

**Сборка (assembly)** — это, соответственно, результат компиляции проекта. Как правило это .exe или .dll файл, содержащий инструкции для компьютера.

**Решение (solution)** — это несколько проектов, объединенные общими библиотеками и задачами. Как правило открывать с помощью Visual Studio нужно именно файл решения (.sln), хотя можно открыть и отдельный проект (.csproj файл). Имейте в виду, если открыть отдельный кодовый файл, не открывая проект или решение, то не будет возможности его запустить. Это распространённая ошибка новичков.

**Reference** — ссылка внутри проекта на другие сборки. Только сославшись на другую сборку можно будет использовать код из неё.

**Метод (method)** — это последовательность действий. Аналог функций, процедур и подпрограмм в других языках. В устной речи часто используют все эти слова как синонимы, но в спецификации на язык C# используется термин «метод».

**Класс (class)** — это совокупность данных и методов. Все сборки состоят из скомпилированных классов.

**Пространство имен (namespace)** — это совокупность классов, логически связанных между собой.
Между сборками и пространствами имен нет прямого соответствия: в сборке может хранится несколько пространств имен, а разные классы одного пространства имен могут быть определены в разных сборках.
После успешной компиляции, в директории проекта создается поддиректория bin/Debug, в которой и оказывается сборка — результат компиляции — exe или dll файлы вашей программы.

**Переменная** — это именованная область памяти.

**Тип переменной** — это формат области памяти, определяющий множество возможных значений переменной и множество допустимых операций над ней.

**Field

**Property - Properties allow you to control the accessibility of a class's variables. A property is much like a combination of a variable and a method - it can't take any parameters, but you are able to process the value before it's assigned to our returned variable. A property consists of 2 parts, a get and a set method, wrapped inside the property.

**Inheritance - Is inheritance, the ability to create classes which inherits certain aspects from parent classes.

<br>




# Main()

The Main method is the entry point of a C# application. (Libraries and services do not require a Main method as an entry point.) When the application is started, the Main method is the first method that is invoked.

There can only be one entry point in a C# program. If you have more than one class that has a Main method, you must compile your program with the StartupObject compiler option to specify which Main method to use as the entry point.

```c#
using System;

class TestClass
{
    static void Main(string[] args)
    {
        // Display the number of command line arguments.
        Console.WriteLine(args.Length);
    }
}
```

<br>




# DataTypes 


| Type       | Description          |Examples  |
| ------------- |:-------------:| -----:|
| `int `    | Integer (whole numbers) | 103, 12, 5168|
| `double`    | 64 bit floating-point number | 3.14, 3.4e38|
| `Float`     | Floating-point number     |   3.14, 3.4e38 |
| `Decimal` | Decimal number (higher precision)      |   1037.196543 |
| `Bool`    | Boolean  | true, False|
| `String`  | String | "Hello World" |
| `byte`  | 8-bit unsigned integer | 0 to 255 |
| `char`  | 16-bit Unicode character | "A" |
| `long`  | 64-bit signed integer type | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |

<br>




# Operators

| Operator      | Description          |Examples  |
| ------------- |:-------------:| -----:|
| `=`    | Assigns a value to a variable.|	i=6
| `+`     | Adds a value or variable.     |  i=5+5 |
| `-` | Subtracts a value or variable.      |   i=5-5 |
| `*`    | Multiplies a value or variable.  | i=5*5
| `/`  | Divides a value or variable.| i=5/5
| `+=`    | Increments a variable. | i += 1|
| `-=`     | Decrements a variable.     |   i -= 1 |
| `==` | Equality. Returns true if values are equal.      |   if (i==10) |
| `!=`    |Inequality. Returns true if values are not equal.  | if (i!=10)
| `<`  | Less Than | if (i<10)
| `<=`    | Greater Than | if (i>10)|
| `>=`     | Less Than or Equal to     |   if (i<=10) |
| `+` | Adding strings (concatenation).   |  "Hello " + "World" |
| `.`    | Dot. Separate objects and methods.  | DateTime.Hour
| `()`  |Parenthesis. Groups values. | (i+5)
| `()`    | Parenthesis. Passes parameters. | x=Add(i,5)
| `[]`  | Brackets. Accesses values in arrays or collections. | name[3]
| `!`    | Not. Reverses true or false. | if (!ready)|
| `&&`     | Logical AND.     |  if (ready && clear) |
| `||` | Logical OR.      |   if (ready || clear) |

<br>




# Params Keyword

```c#
// We can create a function and pass parameters like this
static void GreetPersons(string[] names) { }

// However, calling it would be a bit clumsy. In the shortest form, it would look like this:
GreetPersons(new string[] { "John", "Jane", "Tarzan" });
```

By Adding the keyword params we can call it like this

```c#
static void GreetPersons(params string[] names) { }

// And call it like this,
GreetPersons("John", "Jane", "Tarzan");
```

Another advantage of using the params approach, is that you are allowed to pass ```zero parameters``` to it as well. 

<br>




# Properties

* Properties allow you to control the accessibility of a class's variables
* Recommended way to access variables from the outside in an object oriented programming language like C#
* A property is much like a combination of a variable and a method - it can't take any parameters, but you are able to process the value before it's assigned to our returned variable
* A property consists of 2 parts, a get and a set method, wrapped inside the property:

```c#
private string color;

public string Color
{
    get { return color; }
    set { color = value; }
}
```

> The ```get``` method should ```return``` the variable<br>
> The ```set``` method should ```assign a value``` to it.

However you can add logic and conditionals to the ```Get``` and ```Set``` methods.

```c#
public string Color
{
    get 
    {
        return color.ToUpper(); 
    }
    set 
    { 
        if(value == "Red")
            color = value; 
        else
            Console.WriteLine("This car can only be red!");
    }
}
```

<br>




# Access Modifiers

| Visability       | Definition         | 
| ------------- |:-------------| 
| public    | the member can be reached from anywhere. This is the least restrictive visibility. Enums and interfaces are, by default, publicly visible |
| protected      | members can only be reached from within the same class, or from a class which inherits from this class.      |
| internal | members can be reached from within the same project only.|
| protected internal| the same as internal, except that classes which inherit from this class can reach its members; even from another project.      | 
| private| can only be reached by members from the same class. This is the most restrictive visibility. Classes and structs are by default set to private visibility.      | 

<div align="center">
<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--zkOyN7ci--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/q1zqxeq637m4dksosrni.png" width=60%/>
</div>

<br>




# Inheritance


## Virtual and Override 

Here we take the same principle as above however we override the Greet Method as defined in the Animal Base class. To allow this we have to add the keyword Virtual to the greet method. This then allows us to override that method in the child class dog.

```c#
public class Animal
{
    public virtual void Greet()
    {
        Console.WriteLine("Hello, I'm some sort of animal!");
    }
}

public class Dog : Animal
{
    public override void Greet()
    {
        Console.WriteLine("Hello, I'm a dog!");
    }
}

```

<br>


## Base

In C#, you are not allowed to override a member of a class unless it's marked as ```virtual```. If you want to, you can still access the inherited method, even when you override it, using the ```base keyword```.

```c#
public override void Greet()
{
    /*  
        you can still access the base class
        by using the base keyword
    */

    base.Greet();
    Console.WriteLine("Yes I am - a dog!");
}
```

<br>


## Abstract Class

* Abstract classes, marked by the keyword abstract in the class definition, are typically used to define a base class in the hierarchy
* You ```can't``` create an instance of them.

```c#
// We can't new up an abstract class
abstract class FourLeggedAnimal
    {
        public virtual string Describe()
        {
            return "Not much is known about this four legged animal!";
        }
    }

// We can inherit from it !
class Dog : FourLeggedAnimal
    {

    }

```

<br>


## Abstract methods

* Abstract methods are only allowed within abstract classes. 
* We define them as abstract but without any code
* Then in our inherited class we override that method description .

```c#
abstract class FourLeggedAnimal
	{
	/* 
	   Define the abstract method definition
	   from within the abstract class
	*/
	public abstract string Describe();
	}


    class Dog : FourLeggedAnimal
    {
         /* 
            Override the abstract method definition
            from within the sub class and add 
            code block
        */
        public override string Describe()
        {
            return "I'm a dog!";
        }
    }

```

<br>










# Строки

**Строки** - это последовательности символов

```c#
class Program
{
	public static void Main()
	{
		string myString = "Hello, world!";

		// + — это операция "приписывания" одной строки к другой:
		string s = "Hello" + " " + "world";

		// Можно обращаться к отдельным символам
		char c = myString[1]; //'e' — нумерация символов с нуля.
		char myChar = 'e'; // одинарные кавычки используются для символов. Двойные — для строк.

		//У строк есть собственные методы и переменные (правильно называть это свойствами),
		//которые позволяют узнать информацию о строке 
		Console.WriteLine(myString.Length);

		myString = myString.Substring(0, 5);
		Console.WriteLine(myString);

		string strangeSymbols = "© 2014 Σγμβόλσ";

		//Тип string может иметь особое значение - null.
		//Это не пустая строка, а отсутствие всякой строки.
		myString = null;

		//Интересно, что тип int такого значения иметь не может.
		//int a=null;

		int number = int.Parse("42"); //Из строки в число
		string numString = 42.ToString(); // Из числа в строку
		double number2 = double.Parse("34.42"); // Зависит от настроек операционной системы

		//Следующий вызов не зависит от настроек и всегда ожидает точку в качестве разделителя:
		number2 = double.Parse("34.42", CultureInfo.InvariantCulture);

		//Следующий вызов не зависит от настроек и всегда использует точку в качестве разделителя:
		string invariantNumber2 = number2.ToString(CultureInfo.InvariantCulture);
		Console.WriteLine(invariantNumber2); //34.42
	}
}
```






# Order Of Items In Classes

According to the StyleCop Rules Documentation the ordering is as follows.

### Within a class, struct or interface: (SA1201 and SA1203)
* Constant Fields
* Fields
* Constructors
* Finalizers (Destructors)
* Delegates
* Events
* Enums
* Interfaces (interface implementations)
* Properties
* Indexers
* Methods
* Structs
* Classes

### Within each of these groups order by access: (SA1202)
* public
* internal
* protected internal
* protected
* private

### Within each of the access groups, order by static, then non-static: (SA1204)
* static
* non-static

### Within each of the static/non-static groups of fields, order by readonly, then non-readonly : (SA1214 and SA1215)
* readonly
* non-readonly
