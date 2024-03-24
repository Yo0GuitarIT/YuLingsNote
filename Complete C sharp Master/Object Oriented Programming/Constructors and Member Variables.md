# Constructors and Member Variables

---

```csharp
// Program.cs

namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Car audi = new Car("audi A4",250,"red");
            audi.Drive();
            audi.Details();

            Car bmw = new Car("BMW M5", 350);
            bmw.Drive();
            bmw.Details();

            Console.WriteLine("Press 1 to stop the car!");
            string? userInput = Console.ReadLine();
            if (userInput == "1")
            {
                audi.Stop();
            }
            else
            {
                Console.WriteLine("Car drives indefinetely");
            }
        }
    }
}
```

```csharp
//Car.cs

namespace test
{
    internal class Car
    {
        // private field typically used for storing data.
        // Member variables
        private string _name;
        private int _hp;
        private string _color;

        // Constructor
        public Car(string name, int hp = 0, string color = "gray")
        {
            _name = name;
            _hp = hp;
            _color = color;
            Console.WriteLine($"{name} was created");
        }

        // Member Method
        public void Drive()
        {
            Console.WriteLine($"{_name} is driving");
        }

        // Member Method
        public void Stop()
        {
            Console.WriteLine($"{_name} stoped!");
        }

        public void Details()
        {
            Console.WriteLine($"The car {_name} has {_hp} hp.");
            Console.WriteLine($"It's color is {_color}");
        }
    }
}

```