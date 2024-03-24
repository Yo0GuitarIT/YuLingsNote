# Getting The Min Value of Many Given Numbers Using Params

---

```csharp
using System.Runtime.ConstrainedExecution;

namespace ParaExample
{
    class Program
    {
        static void Main(string[] args)
        {
            int min = MinV2(6, -4, 2, 8, 0, 1, 5); // here we passed 7 values
            int min2 = MinV2(1336,42,69,420,404); // here we passed 5values

            Console.WriteLine("The minimum is {0}.", min);
            Console.WriteLine("The minimum2 is {0}.", min2);
        }

        public static int MinV2(params int[] numbers)
        {
            int min = int.MaxValue; //int最大整數

            foreach (int number in numbers)
            {
                min = number < min ? number : min;
            }
            return min;
        }
    }
}

```
