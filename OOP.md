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
## 1.Encapsulation : ডেটা লুকিয়ে রাখা
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
## 2.Abstract Class : শুধু দরকারি অংশ দেখা
#### 🔹 Abstract class হচ্ছে এমন একটি ক্লাস যেটা থেকে সরাসরি object তৈরি করা যায় না।
#### 🔹 এর মধ্যে abstract method থাকতে পারে — মানে, method টা শুধু ঘোষণা (declare) করা হয়, কিন্তু কাজের body দেওয়া হয় না।
#### 🔹 এর child (derived) class গুলো সেই method এর কাজ বাস্তবায়ন (implement) করে।
```cs
using System;
abstract class Animal
{
    public abstract void MakeSound();  // শুধু define, body নাই
}
class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Dog says Ghew Ghew!");
    }
}
class Program
{
    static void Main()
    {
        Animal dog = new Dog();  // abstract class এর reference
        dog.MakeSound();  // Output: Dog says Ghew Ghew!
    }
}

```
## Polymorphism :একই interface বা method call, কিন্তু আলাদা behavior (আচরণ)
### দুই ধরনের Polymorphism:
#### 1.Compile-time (Method Overloading) – পরে চাইলে এটাও দেখাবো।
#### 2.Runtime (Method Overriding) ✅ তুমি এইটা ইউজ করেছো।
```cs
using System;
class Shape
{
//virtual keyword দিয়ে বোঝানো হয়েছে: এই method কে child class override করতে পারবে।
    public virtual void Draw()
    {
        Console.WriteLine("Drawing shape...");
    }
}

//🔹 Circle class → Shape কে inherit করেছে।
//🔸 এখানে Draw() method কে override করা হয়েছে, তাই এখন Circle এর নিজস্ব behavior হবে।

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing circle...");
    }
}
class Program
{
    static void Main()
    {
        Shape shape1 = new Circle();  // Parent reference দিয়ে Child object
        shape1.Draw();  // Output: Drawing circle!
    }
}


//🔸 Shape shape1 = new Circle(); 👉 এটা Polymorphism। Parent class (Shape) এর reference দিয়ে Child class (Circle) এর object তৈরি করেছো।
//🔸 তারপর shape1.Draw(); কল করলে runtime-এ বুঝে যায় যে এটা Circle এর instance, তাই Circle এর override করা Draw() method চালায়।


```
## Inheritance : উত্তরাধিকার পদ্ধতি
```cs
class Vehicle
{
    public void Start()
    {
        Console.WriteLine("Vehicle is starting...");
    }
}

class Car : Vehicle
{
    public void Drive()
    {
        Console.WriteLine("Car is driving...");
    }
}

class Program
{
    static void Main()
    {
        Car c1 = new Car();
        c1.Start();  // Vehicle class থেকে পাওয়া
        c1.Drive();
    }
}

```






