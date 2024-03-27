# Virtual and Override Keywords

### Example

- Program.cs

```csharp
namespace VirtualOverrideDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Dog dog = new Dog("Sif", 15);
            Console.WriteLine($"{dog.Name} is {dog.Age} years old");
            dog.MakeSound();
            dog.Eat();
            dog.Play();
        }
    }
}
```

- Animal.cs

```csharp
using System.Reflection.Metadata;

namespace VirtualOverrideDemo
{
    class Animal
    {
        // name property
        public string Name { get; set; }

        // age property
        public int Age { get; set; }
        public bool IsHungry { get; set; }

        //simple constructor
        public Animal(string name, int age)
        {
            Name = name;
            Age = age;
            // in our case all our animals are hungry by default ;)
            IsHungry = true;
        }

        // an empty virtual method MakeSound for other classes to overdide
        public virtual void MakeSound() { }

        // a vitual method called Eat which sub classes can override
        public virtual void Eat()
        {
            // check if animal is hungry
            if (IsHungry)
            {
                Console.WriteLine($"{Name} is eating.");
            }
            else
            {
                // otherwise print that the animal is not hungry
                Console.WriteLine($"{Name} is not hungry.");
            }
        }

        // vitrual method Play
        public virtual void Play()
        {
            Console.WriteLine($"{Name} is playing");
        }
    }
}
```

- Dog.cs

```csharp
namespace VirtualOverrideDemo
{
    class Dog : Animal
    {
        // bool property to check if the dog is Happy
        public bool IsHappy { get; set; }

        // simple constructor where we pass the name and age to our base constructor
        public Dog(string name, int age)
            : base(name, age)
        {
            // all dogs are happy ;)
            IsHappy = true;
        }

        // simple overrde of the virtual method Eat
        public override void Eat()
        {
            // to call the eat method from our base class we use the key "base"
            base.Eat();
        }

        public override void MakeSound()
        {
            // since every animal will make a totally different sound
            // each animail will implement their own version od MakeSound
            Console.WriteLine("Wuuuf!.");
        }

        public override void Play()
        {
            // check if the dog is happy if yes call the Play method from the base class
            if (IsHappy)
            {
                base.Play();
            }
        }
    }
}
```

### 說明

_使用了 `virtual` 和 `override` 關鍵字來實現類別的多型性，讓不同類別的物件可以以相同的方式被處理，同時也可以具有自己獨特的行為。_

1. **`virtual` 關鍵字**：

   - 在父類別中，使用 `virtual` 關鍵字聲明的方法表示這個方法可以被子類別重寫。
   - 在 `Animal` 類別中，`MakeSound()` 和 `Eat()` 方法都是虛擬方法，因為不同的動物會發出不同的聲音，並且吃飯的方式也可能不同。

2. **`override` 關鍵字**：

   - 在子類別中，使用 `override` 關鍵字來重寫父類別中被聲明為虛擬的方法。
   - 在 `Dog` 類別中，我們使用 `override` 關鍵字來重寫了 `Eat()` 和 `MakeSound()` 方法，以便為狗定制特定的行為。
   - `Play()` 方法在 `Dog` 類別中也被重寫，但僅在狗快樂時才調用基類別中的 `Play()` 方法，這是因為狗只有在快樂時才會玩耍。

3. **使用方法**：
   - 在 `Main` 方法中，我們創建了一個狗的實例並呼叫了其方法。
   - 狗的實例 `dog` 可以正確地調用 `MakeSound()`、`Eat()` 和 `Play()` 方法，這是因為這些方法在 `Animal` 類別中被聲明為虛擬方法，並在 `Dog` 類別中被正確地重寫了。

> `virtual` 關鍵字用於父類別中聲明方法可被子類別重寫。  
> `override` 關鍵字則用於子類別中實際覆寫父類別中的虛擬方法，這樣可以為不同的類別定制特定的行為，同時保持代碼的結構清晰和易於理解。
