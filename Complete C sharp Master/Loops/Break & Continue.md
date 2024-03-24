# Break & Continue

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            for (int counter = 0; counter < 10; counter++)
            {
                if (counter % 2 == 0)
                {
                    Console.WriteLine($"At {counter}, it's Even!");
                    continue;
                }
                else if (counter == 7)
                {
                    Console.WriteLine($"At {counter} we stop.");
                    break;
                }
                Console.WriteLine(counter);
            }
        }
    }
}

```