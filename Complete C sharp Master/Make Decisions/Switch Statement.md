# Switch Statement

---

```csharp
namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int age = 25;

            switch (age)
            {
                case 15:
                    Console.WriteLine("Too young to party in the club!");
                    break;
                case 25:
                    Console.WriteLine("Good To GO");
                    break;
                default:
                    Console.WriteLine("How old are you then?");
                    break;
            }

            /* if (age == 15) */
            /* { */
            /*     Console.WriteLine("Too young to party in the club!"); */
            /* } */
            /* else if (age == 25) */
            /* { */
            /*     Console.WriteLine("Good To Go!"); */
            /* } */
            /* else */
            /* { */
            /*     Console.WriteLine("How old are you then?"); */
            /* } */

            string username = "Frank";

            switch (username)
            {
                case "Yo0":
                    Console.WriteLine("username is Yo0");
                    break;
                case "root":
                    Console.WriteLine("username is root");
                    break;
                default:
                    Console.WriteLine("username is unknown");
                    break;
            }
        }
    }
}

```