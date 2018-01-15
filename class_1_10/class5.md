# 第 5 課 - 變數

## Scope

### 題目

1. 試著在 button1_Click 裡面宣告兩個「名稱相同」的變數，可以發現甚麼問題？
2. 那如果我分別在 button1_Click 跟 Form1 這兩個 method 中宣告一樣的變數呢？
3. 那或者我在 button1_Click 裡面跟外面(注意不是在 Form1 的 method 中)，宣告名稱一樣的變數呢？

上面這三種情況，為什麼有時候變數可以名稱相同，有時候不行？
(參考補充的 Scope)

### 參考解答

#### 狀況一

首先若在 `button1_Click` 內宣告相同名稱的變數，例如：

```
public partial class Form1 : Form
{
  public Form1()
  {
    InitializeComponent();
  }

  private void button1_Click(object sender, EventArgs e)
  {
    int meow;
    int meow;
  }
}
```

IDE 就會出現錯誤，並提示你這邊使用了相同的變數名稱。

#### 狀況二

不過若是在 `Form1` 與 `button1_Click` 中同時宣告：

```
public partial class Form1 : Form
{
  public Form1()
  {
    InitializeComponent();
    int meow;
  }

  private void button1_Click(object sender, EventArgs e)
  {
    int meow;
  }
}
```

則不會有任何錯誤訊息出現。

#### 狀況三

若在其中一個宣告在 method 外面 (但還是在 class 內)：

```
public partial class Form1 : Form
{
  int meow;

  public Form1()
  {
    InitializeComponent();
  }

  private void button1_Click(object sender, EventArgs e)
  {
    int meow;
  }
}
```

也不會有任何錯誤。

#### 說明

這一切都跟 Scope 有關。

Scope 可以想成是一個變數的「生存範圍」，他代表這個變數在哪個範圍內「有效」。詳情可以參考部落格上的[補充][1]。在 C# 中，一個大原則就是盡量避免名稱衝突。因此在一般狀況下，C# 會限制你不能宣告相同名稱的東西。不過這也是有各種例外存在的。

1. 第一種狀況中，在同一個 scope 內宣告了相同名稱的變數是不被允許的，因此會被判斷為錯誤。
2. 第二種狀況中，`Form1` 跟 `button1_Click` 可以被視為兩個分開的 scope，在他們之內宣告的變數都不會在互相的區域產生效果，因此被 C# 允許。
3. 第三種狀況中，第一個 `meow` 被放在 method 以外的區域，因此他的 scope 就是整個 class。雖然他跟 `button1_Click` 中 `meow` 的 scope 重疊了，但是這在 C# 中是被允許的。因為第一個 `meow` 可以被當作是 class 的屬性。

那麼這時產生另一個問題，在第三種狀況中，若我在 `button1_Click` 內呼叫 `meow` 會用到哪一個呢？

基本上這邊採用「最近原則」，也就是宣告位置離該段程式碼最近的變數會優先使用！也就是用 `button1_Click` 內宣告的 `meow`。

那如果我想使用外面那個 `meow` 怎麼辦？

這邊就要使用到一個特殊的關鍵字 `this`，關於使用方式可以參考[後面的課程][2]。


[1]: http://slmtsite.blogspot.tw/2012/12/c-5.html
[2]: http://slmtsite.blogspot.tw/2013/06/c-18-this.html
