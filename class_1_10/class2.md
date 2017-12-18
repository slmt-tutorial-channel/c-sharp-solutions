# 第2課 - IDE 跟 Hello World

## 第一題：註冊 Visual C# 2010 Express

### 題目

註冊 Visual C# 2010 Express 以延長使用期限！

### 參考解答

現在與這個教學影片當初錄製時的環境已經改變很多，官方現在已經提供限制更少的 Community 版本。因此建議下載 Community 版本會比較好。

下載網址： [Visual Studio 各版本下載][1]

## 第二題：Console.WriteLine

### 題目

試著修改 Console.WriteLine 裡面的文字，讓程式顯示自己的名字吧！

### 參考解答

相信這題應該對大家來說很容易，只要把雙引號中的文字改掉就好。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("我是小山貓！我超強！");
            Console.ReadKey();
        }
    }
}

```

[1]: https://www.visualstudio.com/zh-hant/downloads/
