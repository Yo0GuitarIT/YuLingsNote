# Methods with Return Value & Parameters


```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Add(Add(1, 2), Add(3, 4)));
            Console.WriteLine(Add(15, 31));

            Console.WriteLine(Multiply(25, 25));

            Console.WriteLine(Devide(25, 13));
        }

        public static int Add(int num1, int num2)
        {
            return num1 + num2;
        }

        public static int Multiply(int num1, int num2)
        {
            return num1 * num2;
        }

        public static double Devide(double num1, double num2)
        {
            return num1 / num2;
        }
    }
}
```
