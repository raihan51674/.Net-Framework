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
            int age = 25;
            double pi = -3.14159;
            int year;
              year = 2023;

            Console.WriteLine("Age: " + age + " Year: " + year + "  Name: " + name + "  Max Int: " + int.MaxValue);
        }
    }
}

```
