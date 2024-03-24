# Enhance If Statements - Ternary Operator Challenge

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int intputTemperature = 0;
            string temperatureMessage = string.Empty;
            string inputValue = string.Empty;

            // take input from console
            Console.WriteLine("Enter the Current temperature : ");
            inputValue = Console.ReadLine();

            //validate the input as valid input  integer value
            bool validInteger = int.TryParse(inputValue, out intputTemperature);

            if (validInteger)
            {
                // conditon ? ifTrue : ifFlase
                // if is valid integer then it will check for the conditions using nest ternary operator here.
                temperatureMessage =
                    intputTemperature <= 15
                        ? "it is too cold here"
                        : (
                            intputTemperature >= 16 && intputTemperature <= 28
                                ? "it is cold here"
                                : intputTemperature > 28
                                    ? "it is hot here"
                                    : ""
                        );
                Console.WriteLine(temperatureMessage);
            }
            else
            {
                // in case if the input value is not a valid temperature
                Console.WriteLine("Not a valid Temperature");
            }
        }
    }
}

```