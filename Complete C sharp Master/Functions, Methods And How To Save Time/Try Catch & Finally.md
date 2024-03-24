# Try Catch & Finally

---

```csharp
using System.Globalization;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Please enter a number!");
            string? userInput = Console.ReadLine();

            try
            {
                int userInputAsInt = int.Parse(userInput);
                Console.WriteLine($"Parsed number: {userInputAsInt}");
            }
            catch (FormatException)
            {
                Console.WriteLine("Format exception, Please enter the correct type next time.");
            }
            catch (OverflowException)
            {
                Console.WriteLine(
                    "Overflow exception,the number was too long or to short for int32"
                );
            }
            catch (ArgumentNullException)
            {
                Console.WriteLine("ArgumentNullException, the value was empty(null)");
            }
            finally
            {
                Console.WriteLine("This is call anyways!");
            }
        }
    }
}
```

在 **`catch`** 塊中的參數是用來指定要捕捉的異常的型別。

當 **`try`** 區塊中的程式碼執行時，如果有任何例外發生，系統會尋找與這些例外型別匹配的 **`catch`** 塊，然後執行匹配的塊中的程式碼。

在你提供的程式碼中，有三個不同的 **`catch`** 塊，每個都捕捉一種不同型別的例外：

1. **`catch (FormatException)`**：當使用 **`int.Parse`** 時，如果輸入的字串無法轉換成整數形式，就會拋出 **`FormatException`**。
2. **`catch (OverflowException)`**：如果輸入的數字太大或太小，超出了 **`int`** 的範圍，**`int.Parse`** 會拋出 **`OverflowException`**。
3. **`catch (ArgumentNullException)`**：在你的程式碼中，這個 **`catch`** 塊的目的是處理可能的 **`null`** 引用。

```csharp
using System.Globalization;
using System.Xml.XPath;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int num1 = 5;
            int num2 = 0;
            int result;
            try
            {
                result = num1 / num2;
            }
            catch (Exception)
            {
                Console.WriteLine("Can't Devide by zero!");
            }
        }
    }
}
```