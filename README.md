# C-Sharp-Notes

<br>

# Index<br>

[Hello, World](#Hello-world)<br>


# Hello, world!

```c#
// Подключение пространства имен System.
using System;

// Таким образом вы определяете свое пространство имен Lectures.
namespace Lectures
{
	// Таким образом определяется класс Program.
	class Program
	{
		/*
		 * static - некое волшебное слово, смысл которого будет ясен позднее.
		 * void Main() определяет метод.
		 * Из-за своего названия Main является точкой входа — это метод, 
		 * который будет запущен при выполнении программы.
		 */
		static void Main()
		{
			// Этот код выводит на экран строку
			// Console — это класс, так же как Program, но из пространства имен System.
			Console.WriteLine("Hello, world!");
        }
    }
}
```
