# While Loop

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int counter = 0;
            while (counter < 10)
            {
                Console.WriteLine(counter);
                counter++;
            }

            int peopleCount = 0;
            string enteredText = "";
            while (enteredText.Equals(""))
            {
                Console.WriteLine(
                    "Please press enter to increase amount by one"
                        + " and anything else enter if you want to finish counting"
                );
                enteredText = Console.ReadLine();

                peopleCount++;
                Console.WriteLine($"current people count is {peopleCount}");
            }
            Console.WriteLine(
                $"{peopleCount} people are inside the bus. Press enter to close the program."
            );
        }
    }
}

```