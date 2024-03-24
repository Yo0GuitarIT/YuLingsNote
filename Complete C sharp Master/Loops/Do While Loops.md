# Do While Loops

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int counter = 1;
            do
            {
                Console.WriteLine(counter);
                counter++;
            } while (counter <= 10);

            int lengthOfText = 0;
            string wholeText = "";

            do
            {
                Console.WriteLine("Please enter the name of a friend");
                string nameOfFriend = Console.ReadLine();
                int currentLength = nameOfFriend.Length;
                lengthOfText += currentLength;
                wholeText += nameOfFriend;
            } while (lengthOfText < 20);

            Console.WriteLine($"Thanks, that was enough! {wholeText}");
        }
    }
}

```