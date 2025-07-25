## Class & Object
```js
using System;
class Person
{
    public string name;
    public int age;

    public void SayHello()
    {
        Console.WriteLine("Hello! My name is " + name + " and I am " + age + " years old.");
    }
}

class Program
{static void Main()  {
        Person p1 = new Person();  // object তৈরি
        p1.name = "Raihan";
        p1.age = 22;
        p1.SayHello();
    }
}

```
