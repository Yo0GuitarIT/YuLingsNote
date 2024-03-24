# User Input

### Easy IO:

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            string? input = Console.ReadLine();
            Console.WriteLine(input);
        }
    }
}
```

## Calculate Example:

```csharp
using System.Globalization;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {

            Console.WriteLine(Calculate());
        }

        public static int Calculate(){
            Console.Write("Please enter the first number: ");
            string? number1Input = Console.ReadLine();

            Console.Write("Please enter the second number: ");
            string? number2Input = Console.ReadLine();

            int num1 = int.Parse(number1Input);
            int num2 = int.Parse(number2Input);

            int result = num1 + num2;
            return result;
        }
    }
}

//==============================================================================

using System.Globalization;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            Calculate();
        }

        public static void Calculate()
        {
            Console.Write("Please enter the first number: ");
            string? number1Input = Console.ReadLine();

            Console.Write("Please enter the second number: ");
            string? number2Input = Console.ReadLine();

            int num1 = int.Parse(number1Input);
            int num2 = int.Parse(number2Input);

            int result = num1 + num2;
            Console.WriteLine(result);
        }
    }
}

```
