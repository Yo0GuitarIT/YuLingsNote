# Exercise


## String 1:

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            // string? myName ;
            // Console.Write("Please enter your name and press enter: ");
            // myName = Console.ReadLine();

            // string myNameUpper = String.Format("Upper case : {0}", myName.ToUpper());
            // string myNameLower = String.Format("Lower case : {0}", myName.ToLower());
            // string myNameTrimmed = String.Format("Trimmed case : {0}", myName.Trim());
            // string myNameSubstring = String.Format("Substring value : {0}", myName.Substring(0, 5));

            // Console.WriteLine(myNameUpper);
            // Console.WriteLine(myNameLower);
            // Console.WriteLine(myNameTrimmed);
            // Console.WriteLine(myNameSubstring);

            string? myName;
            Console.Write("Please enter your name and press enter: ");
            myName = Console.ReadLine();

            if (string.IsNullOrEmpty(myName))
            {
                Console.WriteLine("Please enter a name.");
                return;
            }

            string myNameUpper = $"Upper case : {myName.ToUpper()}";
            string myNameLower = $"Lower case : {myName.ToLower()}";
            string myNameTrimmed = $"Trimmed case : {myName.Trim()}";
            string myNameSubstring = $"Substring value : {myName.Substring(0, 5)}";

            Console.WriteLine(myNameUpper);
            Console.WriteLine(myNameLower);
            Console.WriteLine(myNameTrimmed);
            Console.WriteLine(myNameSubstring);
        }
    }
}
```

## String 2

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Enter your first name: ");
            string? firstName = Console.ReadLine();

            Console.Write("Enter your last name: ");
            string? lastName = Console.ReadLine();
            
            string fullName = string.Concat(firstName," ",lastName);
            // string fullName = $"{firstName} {lastName}";

            Console.Write("Enter a character to seach: ");
            char searchInput = Console.ReadLine()[0];

            int searchIndex = fullName.IndexOf(searchInput);
            Console.WriteLine($"Index of character {searchInput} in string is {searchIndex}");
        }
    }
}
```

資料型別 ⇒ [https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2008/ms228360(v=vs.90)?redirectedfrom=MSDN](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2008/ms228360(v=vs.90)?redirectedfrom=MSDN)

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            byte myByte = 255;
            sbyte mySbyte = -128;
            Console.WriteLine($"{myByte}, {mySbyte}");

            int myInt = -22222;
            uint myUint = 12344;
            Console.WriteLine($"{myInt}, {myUint}");

            string string1 = "I control text";
            string string2 = "12345";

            int stringToInt = int.Parse(string2);
            Console.WriteLine(string1);
            Console.WriteLine(stringToInt);
        }
    }
}
```
