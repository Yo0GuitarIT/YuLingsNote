# Nested if statements

---

## Example : Login system

```csharp
namespace test
{
    class Program
    {
        static string username;
        static string password;

        static void Main(string[] args)
        {
            Register();
            Login();
        }

        public static void Register()
        {
            Console.WriteLine("Please enter your username:");
            username = Console.ReadLine();
            Console.WriteLine("Please enter your password:");
            password = Console.ReadLine();
            Console.WriteLine("Registration completed");
            Console.WriteLine("--------------------------------------");
        }

        public static void Login()
        {
            Console.WriteLine("Please enter your username:");
            if (username == Console.ReadLine())
            {
                Console.WriteLine("Please enter your password:");
                if (password == Console.ReadLine())
                {
                    Console.WriteLine("Login Successful");
                }
                else
                {
                    Console.WriteLine("Login fail, wrong password. Restart program.");
                }
            }
            else
            {
                Console.WriteLine("Login fail, wrong username. Restart program.");
            }
        }
    }
}

```