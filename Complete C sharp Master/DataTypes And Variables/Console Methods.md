# Console Methods


There are various methods available in the console class.

Here we are going to refer all console methods which are helpful to take input from the user as well as to stream or to write the output on the console.

### Console Methods Explained

- `Console.Write(”text here”)` - Prints and keeps the cursor on the **same line**.
- `Console.WriteLine(”text here”)` - Prints and puts the cursor in the **next line**.
- `Console.Read()` - Take a single input of type string and it **return the ASCII value of that input**.
- `Console.ReadLine()` - Take a string or integer input and **returns it as the Output** value.
- `Console.ReadKey()` - Take a single input of type string and it **return the KeyInfo**.args

```csharp
static coid Main(string[] args)
{
	Console.WriteLine("HELLO WORLD");
	
	Console.Write("HELLO");
	
	Console.Write("WORLD");
	
	Console.ReadKey();
}
```

```csharp
namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Enter a string and press Enter:");
            string? readInput = Console.ReadLine();
            Console.WriteLine("You have entered {0}", readInput);

            Console.WriteLine("Enter a string and press Enter:");
            int asciiValue = Console.Read();
            Console.WriteLine("ASCII value is {0}", asciiValue);
        }
    }
}
```
