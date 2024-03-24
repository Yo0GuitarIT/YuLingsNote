# Declaring and initializing Arrays and Length Property

---

```csharp
namespace _07__Arrays
{
    class Program
    {
        static void Main(string[] arg)
        {
            // declare and initialize array grades
            int[] grades = new int[5];

            grades[0] = 20;
            grades[1] = 15;
            grades[2] = 12;
            grades[3] = 9;
            grades[4] = 7;

            Console.WriteLine($"grade at index of 0 : {grades[0]}");

            string input = Console.ReadLine();
            // assign value to array grades at index 0;
            grades[0] = int.Parse(input);
            Console.WriteLine($"grade at index of 0 : {grades[0]}");

            //another way of initializing an array
            int[] gradeOfMathStudentsA = { 20, 13, 12, 8, 8 };

            // third way of initializing an array
            int[] gradeOfMathStudentsB = new int[] { 15, 20, 3, 17, 18, 15 };

            Console.WriteLine("Length of gradeOfMathStudentsA : " + gradeOfMathStudentsA.Length);
            Console.WriteLine("Length of gradeOfMathStudentsB : " + gradeOfMathStudentsB.Length);
        }
    }
}

```