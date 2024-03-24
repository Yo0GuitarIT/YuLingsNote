# Nested For Loops And 2D Arrays

---

```csharp
using System;

namespace twoDArray
{
    internal class Program
    {
        static int[,] matrix =
        {
            { 1, 2, 3 },
            { 4, 5, 6 },
            { 7, 8, 9 }
        };

        static void Main(string[] args)
        {
            foreach (int num in matrix)
            {
		            // 無法利用 num 改動數值
                Console.Write(num + " ");
            }

            Console.WriteLine("\nThis is our 2D array printed using nested for loop");
            // Nest for loop
            // outer for loop
            for (int i = 0; i < matrix.GetLength(0); i++)
            {
                // inner for loop
                for (int j = 0; j < matrix.GetLength(1); j++)
                {
                    matrix[i, j] = 0; //改動數值
                    Console.Write(matrix[i, j] + " ");
                }
            }
        }
    }
}
```

### More Exercise

```csharp
using System;

namespace twoDArray
{
    internal class Program
    {
        static int[,] matrix =
        {
            { 1, 2, 3 },
            { 4, 5, 6 },
            { 7, 8, 9 }
        };

        static void Main(string[] args)
        {
            foreach (int num in matrix)
            {
                Console.Write(num + " ");
            }

            Console.WriteLine("\nThis is our 2D array printed using nested for loop");
            // Nest for loop
            // outer for loop
            for (int i = 0; i < matrix.GetLength(0); i++)
            {
                // inner for loop
                for (int j = 0; j < matrix.GetLength(1); j++)
                {
                    if (matrix[i, j] % 2 == 0)
                    {
                        Console.Write(matrix[i, j]);
                    }
                    else
                    {
                        Console.Write(" ");
                    }
                }
            }

            for (int i = 0; i < matrix.GetLength(0); i++)
            {
                for (int j = 0; j < matrix.GetLength(1); j++)
                {
                    if (i == j)
                    {
                        matrix[i, j] = 1;
                    }
                    else
                    {
                        Console.Write(" ");
                    }
                }
            }
            Console.Write("\n");
            foreach (int element in matrix)
            {
                Console.Write(element + " ");
            }

            Console.Write("\n");
            for (int i = 0; i < matrix.GetLength(0); i++)
            {
                Console.WriteLine(matrix[i, i]);
            }

            Console.Write("\n");
            for (int i = matrix.GetLength(0) - 1; i >= 0; i--)
            {
                Console.WriteLine(matrix[2 - i, i]);
            }

            Console.Write("\n");
            for (int i = 0, j = 2; i < matrix.GetLength(0); i++, j--)
            {
                Console.WriteLine(matrix[i, j]);
            }
        }
    }
}
```