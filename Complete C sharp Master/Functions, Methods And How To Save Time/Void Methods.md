# Void Methods

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            WriteSomething();
            WriteSomethingSpecific("I am call an argument and am called from a method");
        }

        // access modifier (static) return type method name (parameter1, parameter2)
        public static void WriteSomething()
        {
            Console.WriteLine("I am call from method");
        }

        public static void WriteSomethingSpecific(string myText)
        {
            Console.WriteLine(myText);
        }
    }
}

```
