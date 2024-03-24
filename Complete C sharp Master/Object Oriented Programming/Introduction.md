# Introduction

---

### Class

- A class is a blue print of an Object
- It has actions/abilities - so called member functions or methods
- and it has properties - so called member variables
- Inheritance possible
- Can be use like a Datatype (e.g. String is a Class)

```csharp
// program.cs
namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Car audi = new Car();
            audi.Drive();

            Car bmw = new Car();

            Console.WriteLine("Press 1 to stop the car!");
            string userInput = Console.ReadLine();
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
// Car.cs
namespace test
{
    internal class Car
    {
        public Car()
        {
            Console.WriteLine("Car was created");
        }

        public void Drive()
        {
            Console.WriteLine("Car is driving");
        }

        public void Stop()
        {
            Console.WriteLine("car stoped!");
        }
    }
}

```