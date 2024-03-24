# Challenge Jagged Array

---

```csharp
namespace jaggedArray
{
    class Program
    {
        static void Main(string[] args)
        {
            string[] joesFamily = new string[] { "Robert", "Matin" };
            string[][] friendArrays = new string[][]
            {
                new string[] { "Andy", "Tim" },
                new string[] { "Lisa", "Laney" },
                new string[] { "Paul", "Cindy" },
                joesFamily,
            };

            foreach (string[] family in friendArrays)
            {
                foreach (string member in family)
                {
                    Console.WriteLine(member);
                }
            }

            for (int i = 0; i < friendArrays.GetLength(0); i++)
            {
                Console.WriteLine(
                    "Hi {0}, I would like to introduce {1} to you.",
                    friendArrays[i][0],
                    friendArrays[i][1]
                );
            }
        }
    }
}
```