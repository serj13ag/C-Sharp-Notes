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
[Safe Casting](#Safe-Casting)<br>
[Lazy Init](#Lazy-Init)<br>
[Lambdas LINQ](#Lambdas-LINQ)<br>


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

**Field**

**Property** - Properties allow you to control the accessibility of a class's variables. A property is much like a combination of a variable and a method - it can't take any parameters, but you are able to process the value before it's assigned to our returned variable. A property consists of 2 parts, a get and a set method, wrapped inside the property.

**Inheritance** - Is inheritance, the ability to create classes which inherits certain aspects from parent classes.

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

Modify your constructor to the following so that it calls the base class constructor:

```c#
class Account
{
    private string mCode;
    private string mName;
    private string mdescription;
    private double mBalance;

    public Account(string code, string name, string description, double balance)
    {
        mCode = code;
        mName = name;
        mdescription = description;
        mBalance = balance;
    }
}

class PartyAccount : Account
{
    private string mAddress;
    private string mPhone;
    
    public PartyAccount(string code, string name, string description, double balance, string address, string phone)
    : base(code, name, description, balance)
    {
        mAddress = address;
	mPhone = phone;
    }
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




# Safe Casting

A better way to cast safely is to use the as operator, which returns null when input is not a string. This also avoids the small performance hit of accessing input twice.

```c#
string text = input as string;
if(text != null)
{
  ...
}
```

The new method of casting safely in C# 7 is to use is with type patterns. Here is an example of how to use is with type patterns to safely cast input to a string.

```c#
if(input is string text)
{
  ...
}
```

<br>




# Lazy Init

### Проверка на null

```c#
class Test
{
    private Blob _blob = null;

    public Blob BlobData
    {
        get
        {
            if (_blob == null)
            {
                _blob = new Blob();
            }

            return _blob;
        }
    }
}
```

### Тернарный оператор ?:

```c#
class Test
{
    private Blob _blob = null;

    public Blob BlobData
    {
        get
        {
            return _blob == null
                ? _blob = new Blob()
                : _blob;
        }
    }
}
```

### is null

Ситуации бывают разные и мы, например, можем столкнуться с такой, в которой у класса Blob перегружен оператор ==. Для этого, вероятно, нам может потребоваться сделать проверку is null вместо == null. Доступно в свежих версиях языка.

```c#
return _blob is null
    ? _blob = new Blob()
    : _blob;
```

### Null-coalescing оператор ??

Ещё больше упростить код нам поможет бинарный оператор ??
Суть его работы такова. Если первый операнд не равен null, то он и возвращается. Если же первый операнд равен null, возвращается второй.

```c#
class Test
{
    private Blob _blob = null;

    public Blob BlobData
    {
        get
        {
            return _blob ?? (_blob = new Blob());
        }
    }
}
```

### Оператор ??=

В C# 8 появился null-coalescing assignment operator, выглядящий вот так ??=
Принцип его работы заключается в следующем. Если первый операнд не равен null, то он просто возвращается. Если первый операнд равен null, то ему присваивается значение второго и возвращается уже это значение.

```c#
class Test
{
    private Blob _blob = null;

    public Blob BlobData
    {
        get
        {
            return _blob ??= new Blob();
        }
    }
}
```

### System.Lazy

В .NET 4.0 появился класс Lazy, позволяющий скрыть всю эту грязную работу от наших глаз. Теперь мы можем оставить только локальную переменную типа Lazy. При обращении к его свойству Value, мы получим объект класса Blob. Если объект был создан ранее, он сразу вернётся, если нет — сначала будет создан.

```c#
class Test
{
    private readonly Lazy<Blob> _lazy = new Lazy<Blob>();

    public Blob BlobData
    {
        get
        {
            return _lazy.Value;
        }
    }
}
```

Так как у класса Blob есть конструктор без параметров, то Lazy сможет создать его в нужный момент без лишних вопросов. Если же нам нужно выполнить какие-то дополнительные действия во время создания объекта Blob, конструктор класса Lazy может принимать ссылку на FuncT

```c#
private Lazy<Blob> _lazy = new Lazy<Blob>(() => new Blob());
```

Теперь давайте сократим запись readonly свойства, благо современный C# позволяет это делать красиво. В конечном итоге выглядеть всё это станет так:

```c#
class Test
{
    private readonly Lazy<Blob> _lazy = new Lazy<Blob>();
    public Blob BlobData => _lazy.Value;
}
```

### LazyInitializer

Ещё есть вариант не оборачивать класс в обёртку Lazy, а вместо этого использовать функционал LazyInitializer. Этот класс имеет один статический метод EnsureInitialized с кучей перегрузок, позволяющих творить всякое, в том числе делать потокобезопасность и писать кастомный код для создания объекта, но основная суть которого заключается в следующем. Проверить, не инициализирован ли объект. Если нет, то инициализировать. Вернуть объект. С использованием данного класса, мы можем переписать наш код так:

```c#
class Test
{
    private Blob _blob;
    public Blob BlobData => LazyInitializer.EnsureInitialized(ref _blob);
}
```

<br>




# Lambdas LINQ

## Projection

### Select

Select() takes each source element, transforms it, and returns a sequence of the transformed values.

```c#
//class Person(string Name, int Age);

var people = new List<Person>
{
    new Person ("Tom", 23),
    new Person ("Bob", 27),
    new Person ("Sam", 29),
    new Person ("Alice", 24)
};
var names = people.Select(u => u.Name);
// Tom, Bob, Sam, Alice
```

### SelectMany

The SelectMany() method is used to "flatten" a sequence in which each of the elements of the sequence is a separate, subordinate sequence.

```c#
// class Company(string Name, List<Person> Staff);
// class Person(string Name);

var companies = new List<Company>
{
    new Company("Microsoft", new List<Person> {new Person("Tom"), new Person("Bob")}),
    new Company("Google", new List<Person> {new Person("Sam"), new Person("Mike")}),
};
var employees = companies.SelectMany(c => c.Staff);
// Tom, Bob, Sam, Mike

var companies = new List<Company>
{
    new Company("Microsoft", new List<Person> {new Person("Tom"), new Person("Bob")}),
    new Company("Google", new List<Person> {new Person("Sam"), new Person("Mike")}),
};
 
var employees = companies.SelectMany(c => c.Staff,
                                    (c, emp)=> new { Name = emp.Name, Company = c.Name });
 
foreach (var emp in employees)
    Console.WriteLine($"{emp.Name} - {emp.Company}");
/*
Tom - Microsoft
Bob - Microsoft
Sam - Google
Mike - Google
*/
```

## Collection Filtration

### Where

Where() returns a new sequence containing all the elements from the target sequence that meet a specified criteria.

```c#
string[] people = { "Tom", "Alice", "Bob", "Sam", "Tim", "Tomas", "Bill" };
 
var selectedPeople = people.Where(p => p.Length == 3);
// Tom, Bob, Sam, Tim

var people = new List<Person>
{
    new Person ("Tom", 23, new List<string> {"english", "german"}),
    new Person ("Bob", 27, new List<string> {"english", "french" }),
    new Person ("Sam", 29, new List<string>  { "english", "spanish" }),
    new Person ("Alice", 24, new List<string> {"spanish", "german" })
};

var selectedPeople = people.Where(p=> p.Age > 25);
// Bob - 27, Sam - 29
```

### OfType()

OfType() is a filter operation and it filters the collection based on the ability to cast an element in a collection to a specified type. It searches elements by their type only.

```c#
// class Person(string Name);
// class Student(string Name): Person(Name);
// class Employee(string Name) : Person(Name);

var people= new List<Person>
{
    new Student("Tom"),
    new Person("Sam"),
    new Student("Bob"),
    new Employee("Mike")
};
 
var students = people.OfType<Student>();
// Tom, Bob
```

## Collection Sorting

### OrderBy(), OrderByDescending()

OrderBy() sorts the elements in the collection based on specified fields in ascending order.
OrderByDescending() sorts the collection based on specified fields in descending order.

```c#
int[] numbers = { 3, 12, 4, 10 };
var orderedNumbers = numbers.OrderBy(n=>n);
// 3, 4, 10, 12
 
string[] people = { "Tom", "Bob", "Sam" };
var orderedPeople = people.OrderBy(p=>p);
// Bob, Sam, Tom

// class Person(string Name, int Age);
var people = new List<Person>
{
    new Person("Tom", 37),
    new Person("Sam", 28),
    new Person("Tom", 22),
    new Person("Bob", 41),
};

var sortedPeople2 = people.OrderBy(p => p.Age);
// Tom - 22, Sam - 28, Tom - 37, Bob - 41
```

## ThenBy(), ThenByDescending()

ThenBy() used for second level sorting in ascending order.<br>
ThenByDescending() used for second level sorting in descending order.

```c#
var sortedPeople2 = people.OrderBy(p => p.Name).ThenByDescending(p=>p.Age);
// Bob - 41, Sam - 28, Tom - 22, Tom - 37
```

## Collection Usage

**Except()** produces the set difference of two sequences.

```c#
string[] soft = { "Microsoft", "Google", "Apple"};
string[] hard = { "Apple", "IBM", "Samsung"};

var result = soft.Except(hard);
// Microsoft, Google
```

**Intersect()** produces the set intersection of two sequences.

```c#
string[] soft = { "Microsoft", "Google", "Apple"};
string[] hard = { "Apple", "IBM", "Samsung"};

var result = soft.Intersect(hard);
// Apple
```

**Distinct()** returns distinct elements from a sequence.

```c#
string[] soft = { "Microsoft", "Google", "Apple", "Microsoft", "Google" };

var result = soft.Distinct();
// Microsoft, Google, Apple
```

**Union()** produces the set union of two sequences.

```c#
string[] soft = { "Microsoft", "Google", "Apple"};
string[] hard = { "Apple", "IBM", "Samsung"};

var result = soft.Union(hard);
// Microsoft, Google, Apple, IBM, Samsung
```

**Concat()** if we don't want to exclude dublicates like in Union()

## Collection Checks and Gets

**All()** determines whether all elements of a sequence satisfy a condition.
**Any()** determines whether any element of a sequence exists or satisfies a condition.

```c#
string[] people = { "Tom", "Tim", "Bob", "Sam" };

bool allHas3Chars = people.All(s => s.Length == 3);     // true
bool allStartsWithT = people.All(s => s.StartsWith("T"));   // false

bool allHasMore3Chars = people.Any(s => s.Length > 3);     // false
bool allStartsWithT = people.Any(s => s.StartsWith("T"));   // true
```

**Contains** determines whether a sequence contains a specified element.

```c#
string[] people = { "Tom", "Tim", "Bob", "Sam" };

bool hasTom = people.Contains("Tom");     // true
bool hasMike = people.Contains("Mike");     // false
```

**FirstOrDefault()** returns the first element of a sequence, or a default value if no element is found.
**LastOrDefault()** returns the last element of a sequence, or a default value if no element is found.

```c#
string[] people = { "Tom", "Bob", "Kate", "Tim", "Mike", "Sam" };

var first = people.FirstOrDefault();  // Tom
var firstWith4Chars = people.FirstOrDefault(s => s.Length == 4);  // Kate
var firstOrDefault = new string[] {}.FirstOrDefault();  // null
```

## Aggregate Operations

**Count()**
**Sum()**
**Min()**
**Max()**
**Average()** 





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
