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
## Function and Method :
#### Function two type : 
#### 1.normal (objet lage):
```cs
class MyClass
{
    public void PublicFunc() { }
    private void PrivateFunc() { }
    protected void ProtectedFunc() { }
    internal void InternalFunc() { }
    protected internal void ProtectedInternalFunc() { }
}
//use Program.cs file
  MyClass obj = new MyClass();
        obj.PublicFunc());
//private and protected jai nah another public func create kore or vitor call korte hobe then obj creat created func ar


//value pass globally use constructor

public class Person
{
    private string name;

    // constructor with parameter
    public Person(string personName)
    {
        name = personName;
    }

    public void PublicFunc()
    {
        Console.WriteLine("Name: " + name);
    }
}
//Manually vabeo parbo

public class MyClass
{
    public void Greet(string name)
    {
        Console.WriteLine("Hello, " + name + "!");
    }

    public int Add(int a, int b)
    {
        return a + b;
    }
}

    // ✅ object create
        MyClass obj = new MyClass();
        obj.Greet("Raihan");

        int result = obj.Add(10, 20);
        Console.WriteLine("Sum: " + result);


```
####  2.static(class এর object ছাড়াই call করা যায়)
```cs
class Utility
{
    public static void ShowInfo() { }
    internal static void LogData() { }
    private static void Calculate() { }
}
//jekon class ar vitor call kora jai
//same vabe program.cs fileo call kora jai
//private jaina
Utility.ShowInfo(); 

```
## All Function type:
```cs
using System;

class Utility
{
  //🟢 Public মানে: যেকোনো জায়গা থেকে (অন্য ক্লাস থেকেও) access করা যাবে।
  //➡️ u.PublicFunction(); দিয়ে call করা হয়েছে।
    public void PublicFunction()
    {
        Console.WriteLine("Public Function");
    }


    // Private মানে: কেবল এই Utility ক্লাসের ভিতরেই access করা যাবে।
    //
    private void PrivateFunction()
    {
        Console.WriteLine("Private Function");
    }
   //🟠 Protected মানে: কেবল Utility এবং এর child (inherited) class-এ access করা যাবে।
    protected void ProtectedFunction()
    {
        Console.WriteLine("Protected Function");
    }
    //🟢 Internal মানে: একই assembly (একই প্রোজেক্ট/ফাইল) এর মধ্যে access করা যাবে।
    internal void InternalFunction()
    {
        Console.WriteLine("Internal Function");
    }
    //🟡 Protected Internal মানে:অন্য assembly থেকে হলেও inheritance থাকলে
   //➡️ তাই এটাও object দিয়ে call করা যায়: u.ProtectedInternalFunction();
    protected internal void ProtectedInternalFunction()
    {
        Console.WriteLine("Protected Internal Function");
    }
    🔴 Private Protected মানে:একই assembly তে থাকতে হবে, এবং inheritance এর মাধ্যমে access করতে হবে।
    private protected void PrivateProtectedFunction()
    {
        Console.WriteLine("Private Protected Function");
    }

    // Function with return and parameter
    public int Multiply(int a, int b)
    {
        return a * b;
    }

    // Static function
    public static void StaticShow()
    {
        Console.WriteLine("Static function");
    }
}

//call
class Program
{
    static void Main(string[] args)
    {
        Utility u = new Utility();

        u.PublicFunction();              // ✅
        u.InternalFunction();            // ✅
        u.ProtectedInternalFunction();   // ✅

        int result = u.Multiply(5, 4);   // ✅ return type
        Console.WriteLine(result);

        Utility.StaticShow();           // ✅ static function call

        // ❌ u.PrivateFunction();          // error: private
        // ❌ u.ProtectedFunction();        // error: protected
        // ❌ u.PrivateProtectedFunction(); // error: inaccessible
    }
}


```
### Method :
```cs
using System;

namespace MethodExample
{
    class ExampleClass
    {
        // Public method: globally accessible
        public void PublicMethod()
        {
            Console.WriteLine("✅ This is a PUBLIC method.");
        }

        // Private method: only accessible inside this class
        private void PrivateMethod()
        {
            Console.WriteLine("🔒 This is a PRIVATE method.");
        }

        // Protected method: accessible from derived class
        protected void ProtectedMethod()
        {
            Console.WriteLine("🛡️ This is a PROTECTED method.");
        }

        // Internal method: accessible within the same project/assembly
        internal void InternalMethod()
        {
            Console.WriteLine("🏢 This is an INTERNAL method.");
        }

        // Protected internal method: accessible from derived class or same assembly
        protected internal void ProtectedInternalMethod()
        {
            Console.WriteLine("🔐 This is a PROTECTED INTERNAL method.");
        }

        // Private protected method: accessible from derived class in same class only
        private protected void PrivateProtectedMethod()
        {
            Console.WriteLine("🕵️‍♂️ This is a PRIVATE PROTECTED method.");
        }

        // Accessing private method from inside
        public void CallPrivate()
        {
            PrivateMethod();
        }

        public void CallPrivateProtected()
        {
            PrivateProtectedMethod();
        }
    }

    // Inherited class for testing protected & private protected
    class SubClass : ExampleClass
    {
        public void CallFromSubClass()
        {
            Console.WriteLine("Inside SubClass:");
            ProtectedMethod(); // ✅ Allowed
            ProtectedInternalMethod(); // ✅ Allowed
            // PrivateProtectedMethod(); // ❌ Not allowed here
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            ExampleClass example = new ExampleClass();

            Console.WriteLine("Access from Main:");

            // Accessing methods
            example.PublicMethod();               // ✅
            example.InternalMethod();             // ✅
            example.ProtectedInternalMethod();    // ✅
            example.CallPrivate();                // ✅ Calls private internally
            example.CallPrivateProtected();       // ✅

            // example.PrivateMethod();           // ❌ Error
            // example.ProtectedMethod();         // ❌ Error
            // example.PrivateProtectedMethod();  // ❌ Error

            // Subclass access
            SubClass sub = new SubClass();
            sub.CallFromSubClass(); // ✅ Calls protected & protected internal
        }
    }
}

```
