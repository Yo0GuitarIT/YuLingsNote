# Polymorphism Parameters

- Programs.cs
```csharp
namespace PolymorphismC
{
    class Program
    {
        static void Main(string[] args)
        {
            List<Car> cars = new List<Car>
            {
                new Audi(200, "red", "A4"),
                new BMW(250, "Blue", "M3"),
            };

            foreach (Car car in cars)
            {
                car.Repair();
            }

            Car bmwZ3 = new BMW(220, "Black", "Z3");
            Car audiA3 = new Audi(280, "Green", "A3");

            bmwZ3.ShowDetails();
            audiA3.ShowDetails();

            BMW bmwM5 = new BMW(300, "Pink", "M5");
            bmwM5.ShowDetails();

            Car carB = bmwM5;
            carB.ShowDetails();
        }
    }
}
```
- Car.cs
```csharp
namespace PolymorphismC
{
    class Car
    {
        public int HP { get; set; }
        public string Color { get; set; }

        public Car(int hp, string color)
        {
            HP = hp;
            Color = color;
        }

        public void ShowDetails()
        {
            Console.WriteLine($"HP : {HP}, Color : {Color}");
        }

        public virtual void Repair()
        {
            Console.WriteLine("Car was repaired!");
        }
    }
}
```
- BMW.cs
```csharp
namespace PolymorphismC
{
    class BMW : Car
    {
        private string brand = "BMW";
        public string Model { get; set; }

        public BMW(int hp, string color, string model)
            : base(hp, color)
        {
            this.Model = model;
        }

        public new void ShowDetails()
        {
            Console.WriteLine($"Brand : {brand}, HP : {HP}, Color : {Color}");
        }

        public override void Repair()
        {
            Console.WriteLine($"The {brand} {Model} is repaired!");
        }
    }
}
```

- Audi.cs
```csharp
namespace PolymorphismC
{
    class Audi : Car
    {
        private string brand = "Audi";
        public string Model { get; set; }

        public Audi(int hp, string color, string model)
            : base(hp, color)
        {
            this.Model = model;
        }

        public new void ShowDetails()
        {
            Console.WriteLine($"Brand : {brand}, HP : {HP}, Color : {Color}");
        }

        public override void Repair()
        {
            Console.WriteLine($"The {brand} {Model} is repaired!");
        }
    }
}
```


### virtual 和 override：

> `virtual` 關鍵字用於基類方法，它聲明方法是可以被子類重寫的。
> 當你在基類中聲明一個方法為 `virtual` 時，表示它是一個可重寫的方法。
> `override` 關鍵字用於派生類中的方法，它表示該方法將重寫（覆蓋）基類中的虛擬方法。使用 `override` 關鍵字，你可以為基類中的虛擬方法提供一個新的實現。

在程式碼中，`Repair` 方法在 `Car` 基類中被聲明為 `virtual`，這意味著它可以被子類重寫。然後，在 `BMW` 和 `Audi` 類中，你使用了 `override` 關鍵字來重寫 `Repair` 方法，提供了這兩個子類自己的實現。

### new：

> `new` 關鍵字用於派生類中的方法或屬性，它表示該方法或屬性是新的，不是對基類的重寫。
> 使用 `new` 關鍵字，你可以在派生類中引入一個新的成員，而不是對基類的成員進行重寫。


在你的程式碼中，`ShowDetails` 方法在 `BMW` 和 `Audi` 類中被聲明為 `new`，這意味著它們引入了一個新的 `ShowDetails` 方法，並不是對基類中的 `ShowDetails` 方法進行重寫。因此，在處理 `BMW` 和 `Audi` 對象時，如果你使用 `Car` 類型的引用，將會調用基類中的 `ShowDetails` 方法，而不是派生類中的 `new` 方法。

`virtual` 和 `override` 用於實現方法的重寫，而 `new` 用於引入新的成員，它們之間的主要區別在於重寫父類成員時是否保留了多型性。

---

```csharp
 BMW bmwM5 = new BMW(300, "Pink", "M5");
 bmwM5.ShowDetails();

 Car carB = bmwM5;
 carB.ShowDetails();
```
比較一下這兩個調用的差異：

1. `bmwM5.ShowDetails();`：這裡我們直接調用了 `bmwM5` 物件的 `ShowDetails` 方法。由於 `bmwM5` 是一個 `BMW` 物件，因此將調用 `BMW` 類中的 `ShowDetails` 方法。這個方法是使用 `new` 關鍵字在 `BMW` 類中重新定義的，因此將顯示 `BMW` 物件的詳細信息。

2. `carB.ShowDetails();`：這裡我們通過一個 `Car` 型別的引用 `carB` 來調用 `ShowDetails` 方法。儘管 `carB` 實際上引用的是一個 `BMW` 物件，但是由於 `ShowDetails` 方法在 `Car` 類中被聲明，且沒有使用 `virtual` 或 `override` 關鍵字，因此將調用 `Car` 類中的 `ShowDetails` 方法。這個方法是在 `Car` 類中定義的，並沒有被 `BMW` 類的 `new` 方法所影響，因此將顯示 `carB` 引用的物件的基本信息。

> 第一個調用直接調用了物件的實際類別中的方法
> 第二個調用通過基類型的引用間接調用了基類中的方法，並不受派生類中的 `new` 方法的影響。
