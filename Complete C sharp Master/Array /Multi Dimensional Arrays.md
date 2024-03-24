# Multi Dimensional Arrays

---

```csharp
namespace _07__Arrays
{
    class Program
    {
        static void Main(string[] arg)
        {
            // declare 2D Array;
            string[,] matrix;

            // declare 3D Array;
            int[,,] threeD;

            // two dimensional array
            int[,] array2D = new int[,]
            {
                { 1, 2, 3 }, // row 0
                { 4, 5, 6 }, // row 1
                { 7, 8, 9 } // row 2
            };

            Console.WriteLine("Central value is {0}", array2D[1, 1]);
            Console.WriteLine("left first value is {0}", array2D[2, 0]);

            string[,,] array3D = new string[,,]
            {
                {
                    { "000", "001" },
                    { "010", "011" },
                    { "Hi there", "What's up" }
                },
                {
                    { "100", "101" },
                    { "110", "111" },
                    { "Another one", "Last entry" }
                }
            };

            Console.WriteLine("The value is {0}", array3D[0, 1, 1]);
            Console.WriteLine("The value is {0}", array3D[0, 2, 1]);
            Console.WriteLine("The value is {0}", array3D[1, 2, 0]);

            string[,] array2DString = new string[3, 2]
            {
                { "one", "two" },
                { "three", "four" },
                { "five", "six" }
            };

            array2DString[1, 1] = "chicken";
            Console.WriteLine("The value is {0}", array2DString[1, 1]);

            // Rank returns the amount od dimensions
            int dimension = array2DString.Rank;
            Console.WriteLine("Dimension is {0}", dimension);

            int[,] array2D2 =
            {
                { 1, 2 },
                { 3, 4 }
            };

            Console.WriteLine(array2D2.Rank);
        }
    }
}

/* 
Output:

Central value is 5
left first value is 7
The value is 011
The value is What's up
The value is Another one
The value is chicken
Dimension is 2
2
*/
```