# Ternary operation

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            //  condition ? first_expression : second_expression;
            //  condition has to be either true or false
            //  The conditional operator is right - associative.
            //  The expression a ? b : c? d : e
            //  is evaluated as a ? b : (c ? d :e),
            //  not as (a? b:c) ? d:e.
            //  The conditional operator cannot be overload.

            // in Celius
            int temperature = -5;
            string stateOfMatter;

            if (temperature < 0)
                stateOfMatter = "solid";
            else
                stateOfMatter = "liquid";
            Console.WriteLine($"State of matter is {stateOfMatter}");

            temperature += 30;

            // in short
            stateOfMatter = (temperature < 0) ? "solid" : "liquid";
            Console.WriteLine($"State of matter is {stateOfMatter}");

            temperature += 100;
            //challenge - add the gas state of matter to the options
            stateOfMatter = temperature > 100 ? "gas" : (temperature > 0 ? "liquid" : "solid");
            Console.WriteLine($"State of matter is {stateOfMatter}");
        }
    }
}

```