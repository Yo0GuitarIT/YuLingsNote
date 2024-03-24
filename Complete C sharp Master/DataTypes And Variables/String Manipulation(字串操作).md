# String Manipulation(字串操作)

---

```csharp
using System;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define few variables
            int age = 31;
            string name = "Alfonso";
            string job = "Developer";

            // 1. string concatenation.
            Console.WriteLine("String Concatenation");
            Console.WriteLine("Hello my name is " + name + ", I am " + age + " years old.");

            // 2. String formatting.
            // string formatting uses index
            Console.WriteLine("String Formatting");
            Console.WriteLine(
                "Hello my name is {0}, I am {1} years old. I'm a {2}.",
                name,
                age,
                job
            );

            // 3. String interpolation.
            // String Interpolation use $ at the start which will allow us write our
            // variables like this {variableName}
            Console.WriteLine("String Interpolation");
            // Console.WriteLine($"Hello my name is {name}, I am {age} years old.", name, age);
            Console.WriteLine($"Hello\nmy name is {name}, I am {age} years old.");

            // 4. Verbatim strings.
            // verbatim strings start with @ and tells the compiler to take the string
            // literally and ignore ant spaces and escape characters like \n
            Console.WriteLine("Verbatim strings");
            Console.WriteLine(
                @"Lorem ipsum dolor sit amet, 
            consectetur adipiscing elit, sed do eiusmod tempor incididunt ut 

            labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
            nisi ut aliquip ex ea commodo consequat."
            );

            // instead of using \\ to write file paths we can use verbatim strings to make it easier
            // if you remove the @ you will get an error became \U, \A and \D are not valid escape characters
            Console.WriteLine(@"/Users/mac/Desktop/test/Program.cs");

            // with verbatim strings even vaild escape characters wont't work
            Console.WriteLine(@"Muahahaha \n you have no power here!");
            Console.WriteLine("Muahahaha \n you have no power here!");
        }
    }
}
```