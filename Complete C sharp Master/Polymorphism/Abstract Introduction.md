# Abstract Introduction

- Shape.cs

```csharp
namespace AbstractClassesC
{
    abstract class Shape
    {
        public string? Name { get; set; }

        public virtual void GetInfo()
        {
            Console.WriteLine($"\nThis is a {Name}");
        }

        public abstract double Volume();
    }
}
```

- Cube.cs

```csharp
namespace AbstractClassesC
{
    class Cube : Shape
    {
        public double Length { get; set; }

        public Cube(double lenghth)
        {
            this.Name = "Cube";
            this.Length = lenghth;
        }

        public override double Volume()
        {
            return Math.Pow(Length, 3);
        }

        public override void GetInfo()
        {
            base.GetInfo();
            Console.WriteLine($"The Cube has a length of {Length}");
            Console.WriteLine($"Volume is {Volume()}");
        }
    }
}
```

- Sphere.cs

```csharp
namespace AbstractClassesC
{
    class Sphere : Shape
    {
        public double Radius { get; set; }

        public Sphere(double radius)
        {
            this.Name = "Sphere";
            this.Radius = radius;
        }

        public override double Volume()
        {
            return Math.PI * Math.Pow(Radius, 3) * 4 / 3;
        }

        public override void GetInfo()
        {
            base.GetInfo();
            Console.WriteLine($"The Sphere has a Radius of {Radius}");
            Console.WriteLine($"Volume is {Volume()}");
        }
    }
}
```

- Program.cs

```csharp
namespace AbstractClassesC
{
    class program
    {
        static void Main(string[] arg)
        {
            Cube mycube = new Cube(3);
            mycube.GetInfo();

            Sphere mySphere = new Sphere(2.5);
            mySphere.GetInfo();
        }
    }
}
```

## **抽象類別和繼承**

這個程式碼範例展示了 C# 中物件導向程式設計中抽象類別和繼承的概念。
以下是主要方面的細分：

**Shape.cs**

- **Shape 類別（抽象）**

  - 這個抽象類別作為各種形狀的藍圖。
  - 它定義了所有形狀共有的屬性和方法：
    - **Name** (public string)：儲存形狀的名稱（例如“Cube”，“Sphere”）。
    - **GetInfo** (public virtual void)：提供基本形狀資訊列印的虛擬方法。它可以被派生類別覆寫。
    - **Volume** (public abstract double)：計算形狀體積的抽象方法。抽象方法缺乏實作細節，必須在具體（非抽象）派生類別中定義。

**Cube.cs**

- **Cube 類別**

  - 這個具體類別繼承自抽象的 Shape 類別。
  - 它添加了一個特定於立方體的屬性：
    - **Length** (public double)：表示立方體邊的長度。
  - 它實作了抽象方法 Volume：
    - **Volume** (public override double)：使用 Math.Pow(Length, 3) 計算立方體的體積。
  - 它覆寫了 GetInfo 方法：
    - **GetInfo** (public override void)：提供有關立方體的更詳細資訊，首先呼叫基類的 GetInfo，然後列印立方體的長度和體積。

**Sphere.cs**

- **Sphere 類別**

  - 這個具體類別也繼承自抽象的 Shape 類別。
  - 它添加了一個特定於球體的屬性：
    - **Radius** (public double)：表示球體的半徑。
  - 它實作了抽象方法 Volume：
    - **Volume** (public override double)：使用 (4/3) _ Math.PI _ Math.Pow(Radius, 3) 計算球體的體積。
  - 它覆寫了 GetInfo 方法：
    - **GetInfo** (public override void)：提供有關球體的更詳細資訊，首先呼叫基類的 GetInfo，然後列印球體的半徑和體積。

**Program.cs**

- **Main 方法**

  - 這個方法創建了 Cube 和 Sphere 類別的實例，展示了如何使用從抽象類別派生的具體類別。
  - 它對每個物件呼叫 GetInfo 方法，分別提供特定於立方體和球體的形狀資訊。

## **抽象的好處**

- **程式碼可重用性**：Shape 類別為形狀定義了共同的基礎，消除了屬性和基本功能（如 GetInfo）的程式碼重複。
- **多態性**：派生類別（Cube 和 Sphere）可以為抽象方法 Volume 提供專門的實作，允許程式碼靈活性和根據每個形狀的需求調整計算。
- **可擴展性**：Shape 類別可以透過創建繼承自它並實作抽象方法 Volume 的新類別來輕鬆擴展以包括新形狀。

**總而言之，抽象通過在基類中捕獲共性並允許在派生類別中進行具體實作來幫助創建更組織、更易於維護和可擴展的程式碼結構。**
