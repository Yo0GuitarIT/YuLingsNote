# IEnumerable Example 1

- Program.cs

  ```csharp
  namespace IEnumerableAndIenumeratorDemo
  {
    class Program
    {
        // 1. IEnumberable<T> for generic collections
        // 2. IEnumberable for non generic collections

        /// <summary>
        /// IEnumberable contains a single method that you must implement when implementing this interface;
        /// GetEnumberator(), which returns an IEnumberator<T> object.
        /// The returned IEnumberator<T> provides the ability to interate through the collection
        /// by exposing a Current property that points at the object we are currently at in the collection.
        /// </summary>

        /// when it is recommended to use the IEnumberable interface:
        /// Your collection represents a massive database table,
        /// You don't want to copy the entire thing into memory and cause performance issues in your application

        /// When it is not recommended to use the IEnumerable interface:
        /// You need to results right away and are possibly mutating / edit the objects later on.
        /// In this case, it is better to use an Array or a list.

        static void Main(string[] args)
        {
            DogShelter shelter = new DogShelter();

            foreach (Dog dog in shelter)
            {
                if (!dog.IsNaughtyDog)
                {
                    dog.GiveTreat(2);
                }
                else
                {
                    dog.GiveTreat(1);
                }
            }
        }
    }
  }
  ```

- DogShelter.cs

```csharp
using System.Collections;
namespace IEnumerableAndIenumeratorDemo
{
// a class name DogShelter this class contains a generic collection of type Dog
// objects of this class can't be used inside a for each loop
// because it lacks an implementation of the IEnumberable interface
class DogShelter:IEnumerable<Dog>
{
// list of type of List<Dog>
public List<Dog> dogs;

        // this constructor will initialize the dog list with some values
        public DogShelter()
        {
            // initialize the dogs list using the collection-initializer
            dogs = new List<Dog>
            {
                new Dog("Csaper", false),
                new Dog("Sif", true),
                new Dog("Oreo", false),
                new Dog("Piexl", false),
            };
        }

        IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
        {
            return dogs.GetEnumerator();
        }

        IEnumerator IEnumerable.GetEnumerator()
        {
            throw new NotImplementedException();
        }
    }

}
```

- Dog.cs

```csharp
namespace IEnumerableAndIenumeratorDemo
{
    class Dog
    {
        // the name of the dog
        public string Name { get; set; }

        // is it a  naughty dog?
        public bool IsNaughtyDog { get; set; }

        // simple constructor
        public Dog(string name, bool isNaughtyDog)
        {
            this.Name = name;
            this.IsNaughtyDog = isNaughtyDog;
        }

        // this method will print how many treats the dog received
        public void GiveTreat(int numberOfTreats)
        {
            // print a message containing the number of treats and the name of the dog
            Console.WriteLine("Dog: {0} said wuoff {1} times!.", Name, numberOfTreats);
        }
    }
}
```
