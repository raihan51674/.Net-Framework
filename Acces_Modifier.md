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
