## .Net Framework fisr run :
```cs
//prohram.cs file
using Beginner.All_Class;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace Beginner
{
    class Program
    {
        static void Main(string[] args)
        {
            FirstsClassRun firstClass = new FirstsClassRun();
            firstClass.SayHello();
        }
    }
}
```
### First class 
```cs
//irstsClassRun.cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Beginner.All_Class
{
    public class FirstsClassRun
    {
        public void SayHello()
        {
            Console.WriteLine("Hello, this is my first class in C#!");
        }
    }
}


```
## User Input
```cs
using System;

namespace Freecodecamp
{
    class Program
    {
        static void Main(string[] args)
        {
            
            Console.Write("Please enter your name: ");
            string name = Console.ReadLine();

            Console.Write("Please enter your age: ");
            int age;
            while (!int.TryParse(Console.ReadLine(), out age) || age < 0)
            {
                Console.Write("Invalid input. Please enter a valid non-negative age: ");
            }

            Console.WriteLine($"Name       : {name}");
            Console.WriteLine($"Age        : {age}");
          
        }
    }
}

```
## Data Type :
```cs
using System;

namespace Freecodecamp
{
    class Program
    {
        static void Main(string[] args)
        {
            string name = "John";
            char letter ='A'
            int age = 25;
            double pi = -3.1415;
            int year;
            year = 2023;

            Console.WriteLine("Age: " + age + " Year: " + year + "  Name: " + name + "  Max Int: " + int.MaxValue);
        }
    }
}

```
### Converting string to numbers and Boolean data type
```cs

            string age = "234";
            int Age=Convert.ToInt32(age);
            double doubleAge = Convert.ToDouble(age);
            bool value = true;
            bool isMale = false;
            Console.WriteLine("Please enter your name: "+doubleAge);


```
### Operator :
```cs

            int age = 23;
            // +,-,*,/,%,++,--
            age += 10;
            age++;
            string name = "John";
            name += " Doe";
          //remainder
         


            Console.WriteLine("Please enter your name: "+age);
            Console.WriteLine("Please enter your name: " + name);


```
## Array :
```c
            int[] numPrint = new int[3] { 1, 2, 3 };

            int[] numbers = new int[4];

            Console.WriteLine("Please enter 4 numbers:");
            for (int i = 0; i < numbers.Length; i++)
            {
                Console.Write($"Enter number {i + 1}: ");
                while (!int.TryParse(Console.ReadLine(), out numbers[i]))
                {
                    Console.Write("Invalid input. Please enter a valid integer: ");
                }
            }
            foreach (int num in numbers)
            {
                Console.WriteLine(num);
            }


            // Optional: Print numPrint array
            Console.WriteLine("\nStatic array values:");
            foreach (int n in numPrint)
            {
                Console.WriteLine(n);
            }
        }
    }
}

```
