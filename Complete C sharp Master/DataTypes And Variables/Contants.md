# Contants

---

`const` 用於宣告常數，這些常數在編譯時就必須知道並且不能在程序的運行過程中更改。

以下是一些注意事項：

1. **初始化值：** `const` 常數在宣告的同時必須被初始化。初始化後就不能再更改。
    
    ```csharp
    const double PI = 3.14159265359;
    ```
    
2. **命名慣例：** 常數的命名慣例是使用大寫字母，並使用底線 `_` 來區分單詞。
    
    ```csharp
    const int WeeksInYear = 52;
    const int MAX_VALUE = 100;
    ```
    
3. **靜態內容：** `const` 常數是靜態的，它們與類別的實例無關聯，屬於類別本身。你可以在類別的任何地方使用這些常數，並且不需要實例化類別。
4. **編譯時解析：** `const` 常數在編譯時解析，這表示編譯器將直接將常數的值插入到使用它的地方。這有助於提高效能，但也意味著你無法在運行時更改這些值。

```csharp
namespace test
{
    // Constant are immutable values which are known
    // at compile time and do not change for the life the program.
    class Program
    {
        //constants are fields
        const double PI = 3.14159265359;
        const int Weeks = 52;
        const int Months = 12;

        // Create  a constant of type string with your birthday as its value
        const string birthday = "25.09.1995";
        const string birthday2 = "09.25.1995";
        const string birthday3 = "1995-09-25";

        static void Main(string[] args)
        {
            Console.WriteLine($"My birthday is always going to be: {birthday}");
        }
    }
}
```