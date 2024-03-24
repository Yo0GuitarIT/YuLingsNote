# Auto Implemented Properties

---

```csharp
// Car.cs

public class Car
{
    // 定義一個自動屬性 MaxSpeed
    public int MaxSpeed { get; set; }
}

```

```csharp
//Program.cs
namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Car myCar = new Car();
            myCar.MaxSpeed = 180;
            Console.WriteLine("Maxspeed is " + myCar.MaxSpeed);
        }
    }
}
```