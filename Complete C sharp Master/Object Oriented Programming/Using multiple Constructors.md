# Using multiple Constructors

---

```csharp
namespace test
{
    internal class Car
    {
        // private field typically used for storing data.
        // Member variables
        private string _name;
        private int _hp;
        private string _color;

        // Default Constructor
        public Car()
        {
            _name = "Car";
            _hp = 0;
            _color = "green";
        }

        // Partial Specification Constructor
        public Car(string name, int hp = 0)
        {
            _name = name;
            _hp = hp;
            _color = "red";
            Console.WriteLine($"{name} was created");
        }

        // Full Specification Constructor
        public Car(string name, int hp, string color)
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