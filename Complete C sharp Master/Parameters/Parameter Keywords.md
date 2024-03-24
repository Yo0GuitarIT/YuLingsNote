# Parameter Keywords

---

```csharp
using System.Runtime.ConstrainedExecution;

namespace ParaExample
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine
		            ("price is {0}, pi is {1}, at is {2}", 32, 3.14, '@');
            Console.WriteLine(
                "{0}+{1}+{2}+{3}+{4}+{5}+{6}+{7}+{8}+{9} = {10}",
                1,
                2,
                3,
                4,
                5,
                6,
                7,
                8,
                9,
                10,
                1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10
            ); 
        }
    }
}

```

```csharp
using System.Runtime.ConstrainedExecution;

namespace ParaExample
{
    class Program
    {
        static void Main(string[] args)
        {
	         ParasMethod(
                "This",
                "is",
                "a",
                "no",
                "no",
                "idea",
                "I",
                "have",
                "no",
                "idea",
                "when",
                "it's",
                "going",
                "end",
                "......"
            ); // i can keep going...
        }

        public static void ParasMethod(params string[] sentence)
        {
            for (int i = 0; i < sentence.Length; i++)
            {
                Console.Write(sentence[i] + " ");
            }
        }
    }
}

// This is a no no idea I have no idea when it's going end ......
```

```csharp
using System.Runtime.ConstrainedExecution;

namespace ParaExample
{
    class Program
    {
        static void Main(string[] args)
        {
            int price = 50;
            float pi = 3.14f;
            char at = '@';
            string book = "The Hobbit";
            ParasMethod2(price, pi, at, book);
            ParasMethod2("Hello", 5.3, '$',"oAo");

        }

        public static void ParasMethod2(params object[] stuff)
        {
            foreach (object obj in stuff)
            {
                Console.Write(obj + " ");
            }
            Console.WriteLine();
        }
    }
}

// 50 3.14 @ The Hobbit 
// Hello 5.3 $ oAo 
```