# For Loops

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            for (int counter = 0; counter < 50; counter += 5)
            {
                Console.WriteLine(counter + " is lower than 50");
            }
            Console.WriteLine("For loop is done");

            for (int i = 1; i < 20; i += 2)
            {
                Console.WriteLine(i);
            }
        }
    }
}
```