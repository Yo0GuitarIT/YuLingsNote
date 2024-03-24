# if…else Statement

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("What's the temperature like?");
            string temperature = Console.ReadLine();
            int numTemp = int.Parse(temperature);

            if (numTemp > 20)
            {
                Console.WriteLine("Shorts are enough today");
            }
            else if (numTemp == 20)
            {
                Console.WriteLine("Pants and Pull Over should be fine");
            }
            else if (numTemp == 30)
            {
                Console.WriteLine("It's super hot!");
            }
            else
            {
                Console.WriteLine("Take the coat");
            }
        }
    }
}

```