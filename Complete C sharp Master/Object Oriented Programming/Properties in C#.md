# Properties in C#

---

```csharp
// Car.cs

// private Member variables/fields
// access modifier private
private string _name; // private field typically used for storing data.
private int _hp;
private string _color;

// the public property
public string Name
{
    get { return _name; }  // get accesser
    set { _name = value; } // set accesser
}

// Default Constructor
public Car()
{
    _name = "Car!!!";
    _hp = 5;
    _color = "green";
}
```

```csharp
// Program.cs

namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Car myCar = new Car();
            myCar.Name = "MyAudioA3";
            myCar.Details();

            Car myCar2 = new Car();
            Console.WriteLine(myCar2.Name);
        }
    }
}
```

---

## 1. 什麼是屬性(properties)？

屬性是C#中用來封裝類中字段的特殊成員。它們提供了對私有字段的安全訪問，同時還可以添加驗證邏輯、計算屬性值等。

### 2. 屬性的組成

一個屬性通常包含兩個部分：

- Getter：用於返回屬性值。
- Setter：用於設置屬性值。

### 3. 屬性的語法

屬性的語法如下所示：

```csharp
public datatype PropertyName
{
    get
    {
        // getter 邏輯
        return someValue;
    }
    set
    {
        // setter 邏輯
        // value 代表了被分配給屬性的值
        // 可以添加驗證邏輯等
    }
}

```

### 4. 屬性的使用

- 在其他類中，您可以像訪問字段一樣訪問屬性，但實際上是調用了相應的getter或setter方法。
- 屬性可用於隱藏數據的實現細節，從而提高代碼的安全性和可讀性。

### 5. 範例

以下是一個包含屬性的範例類：

```csharp
public class Person
{
    private string _name;
    private int _age;

    // 屬性 Name，包含 getter 和 setter
    public string Name
    {
        get
        {
            return _name;
        }
        set
        {
            _name = value;
        }
    }

    // 屬性 Age，包含 getter 和 setter
    public int Age
    {
        get
        {
            return _age;
        }
        set
        {
            if (value >= 0 && value <= 120)
            {
                _age = value;
            }
            else
            {
                throw new ArgumentException("Age must be between 0 and 120.");
            }
        }
    }
}

```

在這個例子中，`Person`類具有兩個屬性：`Name`和`Age`。它們都包含了getter和setter方法，用於獲取和設置相應的私有字段。Age屬性還包含了一些驗證邏輯，確保年齡在合理的範圍內。

---

### Value:

在 C# 中，`value` 是一個特殊的關鍵字，它代表了在設置屬性值時所提供的值。當您使用 setter 來設置屬性值時，您可以通過 `value` 關鍵字來引用這個被分配的值。

舉個例子，假設有一個名為 `Name` 的屬性，其 setter 中有以下語句：

```csharp
public string Name
{
    set
    {
        _name = value;
    }
}

```

當您調用 `Name` 屬性的 setter 時，例如 `obj.Name = "John";`，在這裡 `"John"` 就是 `value`，它是被分配給 `Name` 屬性的值。在 setter 中，`value` 代表了這個被分配的值，您可以將它賦值給相應的私有字段或進行其他操作。