# Implicit & Explicit Conversion

Implicit & Explicit Conversion

```csharp
using System;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            // implicit conversion
            int num = 12390532;
            long bigNum = num;

            float myFloat = 13.37F;
            double myNewDouble = myFloat;

            double myDouble = 13.37;
            int myInt;
            // explicit conversion
            // cast double to int;
            myInt = (int)myDouble;

            //typeConversion
            string mystring = myDouble.ToString(); // "13.37"
            string myFloatString = myFloat.ToString();
            bool sunIsShining = false;

            string myBoolString = sunIsShining.ToString();
            Console.WriteLine(myBoolString);
            Console.Read();
        }
    }
}
```

**Key Points to Remember:**

- Implicit conversion is preferred when it's safe and avoids data loss.
- Explicit conversion (casting) gives the programmer more control but should be used cautiously, especially when converting from larger to smaller data types.
- Certain conversions might not be allowed or might throw exceptions if data loss is inevitable.