# Parsing a String To an Integer

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            string myString = "15";
            string mySecondString = "13";

            int num1 = int.Parse(myString);
            int num2 = int.Parse(mySecondString);

            int resultInt = num1 + num2;

            Console.WriteLine(resultInt);
        }
    }
}
```

## [How to convert a string to a number](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/types/how-to-convert-a-string-to-a-number)