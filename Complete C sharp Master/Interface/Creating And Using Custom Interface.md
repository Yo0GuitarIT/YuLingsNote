# Creating And Using Custom Interface

### Feature

- **Multi-Inheritance**
- Code Readability
- Code Semantics
- Code Maintainability
- Design Patterns

### Code Example

- Program.cs

```csharp
namespace InheritanceDemo2
{
    class Program
    {
        static void Main(string[] args)
        {
            // creating two chair object of type chair
            Chair officeChair = new Chair("Brown", "Plastic");
            Chair gamingChair = new Chair("Red", "Wood");

            // creating a new object of type car
            Car damagedCar = new Car(80f, "Blue");

            // add the two chairs to the IDestoryable list of the car
            // so that when we destory the car, the destroyable objects
            // that are near the car will get destoryed as well.

            damagedCar.DestoryablesNearby.Add(officeChair);
            damagedCar.DestoryablesNearby.Add(gamingChair);

            damagedCar.Destory();
        }
    }
}
```

- Vehicle.cs

```csharp
namespace InheritanceDemo2
{
    class Vehicle
    {
        // speed of the vehicle
        public float Speed { get; set; }

        // color of the vehicle
        public string Color { get; set; }

        //default constructor
        public Vehicle()
        {
            this.Speed = 120f;
            this.Color = "White";
        }

        // simple constructor
        public Vehicle(float speed, string color)
        {
            this.Speed = speed;
            this.Color = color;
        }
    }
}
```

- Car.cs

```csharp
using System.Data;

namespace InheritanceDemo2
{
    class Car : Vehicle, IDestoryable
    {
        // implementinf the interface's property
        public string DestructionSound { get; set; }

        // creating a new property to store the destoryable objects nearby
        // when a car gets destoryed it should also destory the nearby object
        // this list is of type IDestoryable which means it can store any object
        // that implement this interface and we can only access the properties and
        // methods in this interface.
        public List<IDestoryable> DestoryablesNearby;

        // simple constructor
        public Car(float speed, string color)
            : base(speed, color)
        {
            // initialize the inteface's property with a value in the constructor
            DestructionSound = "CarExplosionSound.mp3";
            // initialize the list of destoryable objects
            DestoryablesNearby = new List<IDestoryable>();
        }

        // implement the interface's method
        public void Destory()
        {
            // when a car gets destoryed we should play the destruction sound
            // and create fire effect
            Console.WriteLine("Playing destruction sound {0}", DestructionSound);
            Console.WriteLine("Create fire");

            // go through each destoryable object nearby and call it's destort method
            foreach (IDestoryable destoryable in DestoryablesNearby)
            {
                destoryable.Destory();
            }
        }
    }
}
```

- Funiture.cs

```csharp
namespace InheritanceDemo2
{
    class Funiture
    {
        // color of the funiture
        public string Color { get; set; }

        // material of the funiture
        public string Material { get; set; }

        // default constructor
        public Funiture()
        {
            this.Color = "White";
            this.Material = "Wood";
        }

        // simple constructor
        public Funiture(string color, string material)
        {
            this.Color = color;
            this.Material = material;
        }
    }
}
```

- Chair.cs

```csharp
namespace InheritanceDemo2
{
    // subclass chair that extends Funiture
    class Chair : Funiture, IDestoryable
    {
        // implementing the interface's property
        public string DestructionSound { get; set; }

        // simple constructor
        public Chair(string color, string material)
            : base(color, material)
        {
            // initializring the interface's proprty with a value in the constructor
            DestructionSound = "ChairDestructionSound.mp3";
        }

        // implementing the interface's method
        public void Destory()
        {
            // when a chair gets destoryed we should play the destruction sound
            // and spawn the destroyed chair parts
            Console.WriteLine($"The {Color} chair was destoryed");
            Console.WriteLine($"Playing destruction sound {DestructionSound}");
            Console.WriteLine("Spawn chair parts");
        }
    }
}
```
