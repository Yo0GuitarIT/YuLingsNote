# If Statements (2) Exercise

```csharp
namespace test
{
    class Program
    {
        static int highScore = 300;
        static string highScorePlayer = "Yo0";

        static void Main(string[] args)
        {
            CheckHighScore(250, "Andy");
            CheckHighScore(315, "Olivia");
            CheckHighScore(350, "Yo0");
        }

        public static void CheckHighScore(int score, string playName)
        {
            if (score > highScore)
            {
                highScore = score;
                highScorePlayer = playName;

                Console.WriteLine($"New High Score is {highScore}");
                Console.WriteLine($"It is new held by {highScorePlayer}");
            }
            else if (score < highScore)
            {
                Console.WriteLine(
                    $"The old highscore could not be broken. It's still {highScore} and held by {highScorePlayer}"
                );
            }
        }
    }
}

```