# Has-A Relationships
### 說明
1. **使用方式：**
   - `Has-a` 關係用於描述類與類之間的組合關係，其中一個類擁有另一個類的一個對象作為成員變量。
   - 在程式碼中，通常將一個類的對象作為另一個類的成員變量，以實現 has-a 關係。

2. **特色：**
   - 提供了組合的方式，使得程式碼更具靈活性和可擴展性。
   - 允許一個類包含其他類的功能，並將其封裝為自己的一部分。
   - 可以通過 `has-a` 關係將不同的類組合在一起，形成更複雜的對象結構。

3. **和Polymorphism 多型之間的關係：**
   - `Has-a` 關係和多型性通常是相輔相成的，但它們描述的是不同層面的程式設計概念。
   - 多型性允許使用相同的介面來處理不同類型的對象，從而實現代碼的靈活性和可擴展性。
   - `Has-a` 關係提供了組合的方式，而多型性則允許使用統一的介面來處理這些組合的對象，從而實現了更強大和更靈活的程式結構。

*`has-a` 關係是一種組合關係，用於描述類與類之間的結合方式，提供了組合和封裝功能的方式，使得程式碼更具彈性和可擴展性。和多型性一起使用時，可以實現更強大和更靈活的程式設計模式。*

### Example
1. **創建一個新的類別 `CarIDInfo.cs`** 

- CarIDInfo.cs

```csharp
namespace PolymorphismC
{
    // Has a
    class CarIDInfo
    {
        public int IDNum { get; set; } = 0;
        public string Owner { get; set; } = "No Owner";
    }
}
```

2. **Write relationships in `Car.cs`**

- Car.cs
```csharp
namespace PolymorphismC
{
    class Car
    {
        public int HP { get; set; }
        public string Color { get; set; }

        // has a relationship////////////////////////////////
        protected CarIDInfo carIDInfo = new CarIDInfo();

        public void SetCardIDInfo(int idNum, string owner)
        {
            carIDInfo.IDNum = idNum;
            carIDInfo.Owner = owner;
        }
        // has a relationship////////////////////////////////
        
        public void GetCardIDInfo()
        {
            Console.WriteLine(
                $"The car has the ID of {carIDInfo.IDNum} and it ia ownwd by {carIDInfo.Owner}"
            );
        }

        public Car() { }

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

3. **因為`BMW`繼承了`Car`的特性，因此`BMW`也擁有`CarIDInfo`的關係，所以可以直接在`Program.cs`裡面直接可以使用`CarIDInfo`的Method.**
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

            // 使用 CardIDInfo
            bmwZ3.SetCardIDInfo(1234, "Ann");
            audiA3.SetCardIDInfo(6789, "Frank");

            bmwZ3.GetCardIDInfo();
            audiA3.GetCardIDInfo();
        }
    }
}
```
