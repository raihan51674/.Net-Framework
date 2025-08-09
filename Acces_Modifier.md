# 1️⃣ Access Modifier কী?

### Access Modifiers হলো কোন ক্লাস, মেথড, বা ভ্যারিয়েবল কোথা থেকে অ্যাক্সেস করা যাবে সেটার নিয়ম।  
### এগুলো নির্ধারণ করে:  
- ক্লাসের বাইরে থেকে মেম্বার দেখা যাবে কিনা।  
- সাবক্লাসে (inheritance হলে) ব্যবহার করা যাবে কিনা।  
- অন্য namespace বা assembly থেকে অ্যাক্সেস করা যাবে কিনা।  

---

## 2️⃣ C#-এর Access Modifiers এর ধরন  
C#-এ মোট 6 ধরনের access modifier আছে:

- private  
- protected  
- internal  
- protected internal  
- private protected  
- public  

---

### Step 1: private

```csharp
class Animal {
    private string name;
}

```
- শুধুমাত্র একই ক্লাসের ভিতর থেকে অ্যাক্সেসযোগ্য।

 - অন্য কোন ক্লাস বা সাবক্লাস থেকেও দেখা যায় না।

- ✅ ব্যবহার: ডেটা হাইডিং বা এনক্যাপসুলেশন এর জন্য।
- ❌ অবজেক্ট দিয়েও বাইরে থেকে অ্যাক্সেস করা যায় না।

# Step 2: protected
```cs
class Animal {
    protected string species;
}
class Dog : Animal {
    void Show() {
        Console.WriteLine(species); // ✅ ইনহেরিট করলে ব্যবহার করা যাবে
    }
}
```
- কেবলমাত্র সাবক্লাসে (inheritance) ব্যবহার করা যায়।

- অবজেক্ট দিয়ে বাইরে থেকে অ্যাক্সেস করা যায় না।

- ✅ ব্যবহৃত হয় ইনহেরিট করা ক্লাসে ডেটা শেয়ার করার জন্য।
 ## Step 3: internal
```cs
class Animal {
    internal int age;
}
class Zoo {
    void Show() {
        Animal obj = new Animal();
        Console.WriteLine(obj.age); // ✅ একই namespace বা assembly-তে অ্যাক্সেসযোগ্য
    }
}
```
- একই namespace বা একই assembly এর মধ্যে থাকলে যেকোন ক্লাস থেকে অ্যাক্সেসযোগ্য।

- অন্য namespace বা অন্য project-এ সরাসরি অ্যাক্সেস করা যাবে না।

-✅ একই প্রজেক্টের মধ্যে ডেটা শেয়ার করার জন্য।
## Step 4: protected internal
```
class Animal {
    protected internal string habitat;
}
class Dolphin : Animal {
    void Show() {
        Console.WriteLine(habitat); // ✅ ইনহেরিট করলে অ্যাক্সেসযোগ্য
    }
}
```
- protected OR internal – যেকোনো একটা শর্ত পূরণ হলেই অ্যাক্সেসযোগ্য।

- মানে:

- একই namespace হলে দেখা যাবে।

- সাবক্লাস হলে অন্য namespace থেকেও দেখা যাবে।

- ✅ ইনহেরিট করা ক্লাসে এবং একই namespace এ ব্যবহারযোগ্য।
 ## Step 5: private protected
```cs
class Animal {
    private protected string tag;
}
class Mammal : Animal {
    void Show() {
        Console.WriteLine(tag); // ✅ হ্যাঁ, কারণ একই namespace এবং ইনহেরিটেড
    }
}
```
- private + protected এর মিশ্রণ।

- কেবল:

- সাবক্লাস হলে ✅

- একই namespace (assembly) হলে ✅

- ❌ অন্য namespace-এ ইনহেরিট করলে অ্যাক্সেসযোগ্য নয়।
## Step 6: public
```cs
class Animal {
    public string type;
}
class Zoo {
    void Show() {
        Animal obj = new Animal();
        Console.WriteLine(obj.type); // ✅ সব জায়গায় অ্যাক্সেসযোগ্য
    }
}
```
- যেকোনো জায়গা থেকে অ্যাক্সেস করা যায়।

- সবচেয়ে বেশি ব্যবহার হয় মেথড, প্রপার্টি বা ক্লাসের জন্য।

# ✅ সহজ ভাষায় মনে রাখার নিয়ম:
- Modifier	সহজ ব্যাখ্যা
- private	কেবল নিজের বাড়ি।
- protected	নিজের আর সন্তানের বাড়ি।
- internal	নিজের এলাকা (namespace)।
- protected internal	সন্তান বা নিজের এলাকা যেকোনো এক হলে।
- private protected	সন্তান + নিজের এলাকা দুটোই হতে হবে।
- public	সবার জন্য উন্মুক্ত।







