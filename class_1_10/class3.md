# 第 3 課 - 程式結構與進入點

## 第一題：多行文字

### 題目

試著讓程式顯示多行的文字
例如：

```text
C# 真好玩
而且我會寫第一個程式了
這是第三行的說
```

### 參考解答

基本上這題就是希望大家能夠試著多用幾次 `Console.WriteLine` 顯示文字：

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
            Console.WriteLine("C# 真好玩");
            Console.WriteLine("而且我會寫第一個程式了");
            Console.WriteLine("這是第三行的說");
            Console.ReadKey();
        }
    }
}
```

## 第二題：停頓再顯示

### 題目

接上一題，試著讓程式顯示一行停頓一次。每次停頓時，必須要按下鍵盤按鍵才會繼續。

### 參考解答

這題希望讓大家正確理解到 `Console.ReadKey` 這個 method 的功能。每用一次，程式就會等待使用者按任一按鍵才會繼續。

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
            Console.WriteLine("C# 真好玩");
            Console.ReadKey();
            Console.WriteLine("而且現在要再按一下才會顯示東西 >///<");
            Console.ReadKey();
            Console.WriteLine("再按一次就結束囉~~~");
            Console.ReadKey();
        }
    }
}
```

## 第三題：嘗試其他 Console 的功能

### 題目

根據「相關資訊連結」的「[Console 可以使用的 method 清單][1]」，查查看還有甚麼其他 method 可以使用。例如：讓電腦發出 Beep 的一聲。

### 參考解答

以下就以 Beep 聲為例。

看一下提供的[文件][1]就可以發現有一個名為 `Beep()` 的 method，其功能寫著「透過主控台喇叭播放嗶聲。」

因此只要在程式碼中加入 `Console.Beep()` ，就可以讓程式發出「嗶！」的聲音。

以下示範使用：

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
            Console.WriteLine("按一下發出聲音");
            Console.ReadKey();
            Console.Beep();
            Console.WriteLine("聽到了嗎？沒聽到的話再試一次！");
            Console.ReadKey();
            Console.Beep();
            Console.WriteLine("結束囉~");
            Console.ReadKey();
        }
    }
}
```

[1]: https://msdn.microsoft.com/zh-tw/library/system.console_methods(v=vs.110).aspx
