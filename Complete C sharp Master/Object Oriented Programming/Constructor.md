# Constructor

---

## **簡介**

C# 中的 constructor 是用來初始化物件的特殊方法。

當一個新的物件被建立時，constructor 會自動被呼叫。

## **語法**

constructor 的語法如下：

```csharp
[修飾詞] class_name([parameter_list]) {
  // 建構函式的程式碼
}
```

其中：

- `[修飾詞]` 可以是 `public`、`internal`、`protected` 或 `private`。
- `class_name` 是類別的名稱。
- `[parameter_list]` 是建構函式的參數列表。

## **預設建構函式**

如果類別沒有定義任何建構函式，編譯器會自動產生一個預設建構函式。預設建構函式沒有任何參數，會將物件的所有欄位初始化為預設值。

## **自訂建構函式**

可以為類別定義自訂建構函式，以初始化物件的欄位。自訂建構函式可以有參數，以接收初始化物件時所需的資料。

## **建構函式的使用**

constructor 可以用於以下用途：

- 初始化物件的欄位。
- 執行物件建立時的初始化邏輯。
- 限制物件的建立方式。

## **例子**

以下是一個簡單的例子：

```csharp
public class Person {
  public string Name { get; set; }
  public int Age { get; set; }

  public Person(string name, int age) {
    Name = name;
    Age = age;
  }
}
```

這個例子中，`Person` 類別有一個建構函式，該建構函式接受兩個參數：`name` 和 `age`。建構函式會將 `name` 和 `age` 分別賦值給 `Name` 和 `Age` 屬性。

以下是如何使用建構函式建立物件的例子：

**C#**

`var person = new Person("John Doe", 30);`

這個程式碼會建立一個新的 `Person` 物件，並將其 `Name` 屬性設定為 "John Doe"，`Age` 屬性設定為 30。

## **進階用法**

constructor 還有一些進階用法，例如：

- 使用建構函式來執行物件建立時的初始化邏輯。
- 使用建構函式來限制物件的建立方式。

以下是一個使用建構函式來執行物件建立時的初始化邏輯的例子：

```csharp
public class Person {
  public string Name { get; set; }
  public int Age { get; set; }

  public Person(string name, int age) {
    if (age < 0) {
      throw new ArgumentException("Age cannot be negative.");
    }

    Name = name;
    Age = age;
  }
}
```

這個例子中，`Person` 類別的建構函式會檢查 `age` 參數是否為負數。如果為負數，則會擲出一個 `ArgumentException` 例外。

以下是一個使用建構函式來限制物件的建立方式的例子：

```csharp
public class Singleton {
  private static Singleton instance;

  private Singleton() { }

  public static Singleton Instance {
    get {
      if (instance == null) {
        instance = new Singleton();
      }

      return instance;
    }
  }
}
```

這個例子中，`Singleton` 類別的建構函式是私有的。這意味著只能在類別本身內部建立 `Singleton` 物件。因此，可以確保只能存在一個 `Singleton` 物件。

## **結論**

constructor 是 C# 中的重要功能，可以用來初始化物件和執行物件建立時的初始化邏輯。了解 constructor 的用法可以幫助您編寫更健壯和可維護的程式碼。

## **參考資源**

- C# Constructors - Microsoft Docs: [https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-struct%3C/2%3Es/constructors)
- C# Constructors - W3Schools: [https://www.w3schools.com/cs/cs_constructors.php](https://www.w3schools.com/cs/cs_constructors.php)