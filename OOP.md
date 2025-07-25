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
## Encapsulation :
#### "ডেটা (variable) এবং ফাংশন (method) কে একসাথে একটি class-এর ভিতরে রেখে বাইরের দুনিয়া থেকে সরাসরি access আটকানো, এবং controlled way তে access দেওয়া।"
```cs
using System;
class Student
{
    private string name;  // ❌ বাইরের কেউ সরাসরি access করতে পারবে না
       public void SetName(string newName)
    {
        name = newName;
    }
       public string GetName()
    {
        return name;
    }
  class Program
{
    static void Main()
    {
        Student s = new Student();
        s.SetName("Raihan"); // ✅ Public method দিয়ে সেট করা হচ্ছে
        Console.WriteLine("Name: " + s.GetName()); // ✅ Public method দিয়ে পাওয়া যাচ্ছে
    }
}

```






