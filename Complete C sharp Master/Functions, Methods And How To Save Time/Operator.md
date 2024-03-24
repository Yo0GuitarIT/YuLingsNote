# Operator

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int num1 = 5;
            int num2 = 3;
            int num3;

            // unary operators
            num3 = -num1;
            Console.WriteLine($"num3 is {num3}.");

            bool isSunny = true;
            Console.WriteLine($"is it sunny? {isSunny}");

            // increment  operators
            int num = 0;
            num++;
            Console.WriteLine($"num is {num}.");
            Console.WriteLine($"num is {num++}.");
            //pre increment
            Console.WriteLine($"num is {++num}.");

            //decrement operators
            num--;
            Console.WriteLine($"num is {num}.");
            Console.WriteLine($"num is {num--}.");
            //pre decrement
            Console.WriteLine($"num is {--num}.");

            int result = num1 + num2;
            Console.WriteLine($"Result of num1 + num2 is {result}");
            result = num1 - num2;
            Console.WriteLine($"Result of num1 - num2 is {result}");
            result = num1 * num2;
            Console.WriteLine($"Result of num1 * num2 is {result}");
            result = num1 / num2;
            Console.WriteLine($"Result of num1 / num2 is {result}");
            result = num1 % num2;
            Console.WriteLine($"Result of num1 % num2 is {result}");

            //Relational and type operators
            bool isLower;
            isLower = num1 > num2;
            Console.WriteLine($"Result of num1 > num2 is {isLower}");

            // equality operator
            bool isEqual;
            isEqual = num1 == num2;
            Console.WriteLine($"Result of num1 == num2 is {isEqual}");
            isEqual = num1 != num2;
            Console.WriteLine($"Result of num1 != num2 is {isEqual}");

            // condition operators
            bool isLowerSunny;
            // condition1 AND conditon2
            isLowerSunny = isSunny && isLower;
            Console.WriteLine($"Result of isLower && isSunny is {isLowerSunny}");

            // condition1 OR conditon2
            isLowerSunny = isSunny || isLower;
            Console.WriteLine($"Result of isLower || isSunny is {isLowerSunny}");
        }
    }
}

```