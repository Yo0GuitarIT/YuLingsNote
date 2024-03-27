# IEnumeriable Example

- Program.cs

```csharp
using System.IO.Pipes;

namespace IEnumerableDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // creat a generic  IEnumerable variable that takes any collection of type int
            // we will use ths variable store the collections
            // that will get returned by the GetCollection() method
            IEnumerable<int> unknownCollection;
            unknownCollection = GetCollection(1);
            Console.WriteLine("This was a list<int>");
            // foreach number in the collection we got back from GetCollection(1);
            foreach (int num in unknownCollection)
            {
                Console.Write(num + " ");
            }

            // new line
            Console.WriteLine(" ");

            // Call GetCollection() when option is 2 which will return Queue<int>
            // but we will store it in the base type of generic collections
            unknownCollection = GetCollection(2);
            Console.WriteLine("This was a Queue<int>");
            // foreach number in the collection we got back from GetCollection(2);
            foreach (int num in unknownCollection)
            {
                Console.Write(num + " ");
            }
            Console.WriteLine(" ");

            unknownCollection = GetCollection(5);
            Console.WriteLine("This was an array of int");
            // foreach number in the collection we got back from GetCollection(2);
            foreach (int num in unknownCollection)
            {
                Console.Write(num + " ");
            }
        }

        static IEnumerable<int> GetCollection(int option)
        {
            // creat a list of numbers and initilize it
            List<int> numbersList = new List<int> { 1, 2, 3, 4, 5 };

            // Add value to the queue
            Queue<int> numbersQueue = new Queue<int>();
            numbersQueue.Enqueue(6);
            numbersQueue.Enqueue(7);
            numbersQueue.Enqueue(8);
            numbersQueue.Enqueue(9);
            numbersQueue.Enqueue(10);

            // if the option is 1
            if (option == 1)
            {
                //turn the list of type List<int>
                return numbersList;
            }
            // if the option is 2
            else if (option == 2)
            {
                // return the queue of type
                return numbersQueue;
            }
            else
            {
                // return an array of numbers initialized with some numbers
                return new int[] { 11, 12, 13, 14, 15 };
            }
        }
    }
}
```
