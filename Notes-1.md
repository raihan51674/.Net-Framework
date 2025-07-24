## .Net Framework fisr run :
```js
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
```js
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
