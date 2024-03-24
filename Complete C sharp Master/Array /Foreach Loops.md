# Foreach Loops

---

```csharp
namespace _07__Arrays
{
    class Program
    {
        static void Main(string[] arg)
        {
            int[] nums = new int[10];
            for (int i = 0; i < nums.Length; i++)
            {
                // 0 => 0
                // 1 => 1
                // ...

                nums[i] = i + 10;
                // Console.WriteLine($"Element{i} = {nums[i]} ");
            }

            int counter = 0;
            foreach (int k in nums)
            {
                Console.WriteLine($"Element{counter} = {k} ");
                counter += 1;
            }

            // Creat an array with 5 of your friends
            // Creat a foreach loop which greets all of them
            string[] myFrinds = { "Micheal", "Anna", "Ina", "Andy", "Cindy" };

            foreach (string name in myFrinds)
            {
                Console.WriteLine($"Hi there {name} is my friend");
            }
        }
    }
}
```

---

### Why ForEach?

```csharp
namespace _07__Arrays
{
    class Program
    {
        static void Main(string[] arg)
        {
            int[] numbers = { 1, 2, 3, 4, 5 };
            foreach (int number in numbers)
            {
                Console.WriteLine(number);
            }

            for (int i = 0; i < numbers.Length; i += 2)
            {
                Console.WriteLine(numbers[i]);
            }

            string input;
            do
            {
                Console.WriteLine("Please enter a valid number:");
                input = Console.ReadLine();
            } while (!int.TryParse(input, out _));
            
            // out _ 表示您不關心轉換後的整數值是什麼，只是想檢查輸入的字串是否可以成功轉換為整數。
            // 因此，您將 _ 作為 TryParse 方法的 out 參數，這樣就可以忽略轉換後的整數值，只需檢查轉換是否成功。
        }
    }
}
```

- 使用 foreach 迴圈遍歷整個 `numbers` 陣列並打印每個元素。
- 使用 for 迴圈以步進為 2 的方式遍歷 `numbers` 陣列並打印每個元素。
- 使用 do while 迴圈來提示用戶輸入一個有效的數字，直到用戶輸入了一個有效的數字（即可以成功轉換為整數）為止。

1. **foreach 迴圈**：
    - 當您想要簡單地遍歷整個陣列，而不需要跟踪索引時，foreach 迴圈是最方便的選擇。它會自動遍歷陣列中的每個元素，並在每次迭代中將元素提取到指定的變數中。
    - foreach 迴圈的語法也比較簡潔，通常用於遍歷並處理陣列中的元素。
2. **for 迴圈**：
    - 當您需要根據索引進行更精細的控制，例如在某些特定條件下訪問特定元素，或者以不規則的步進遍歷陣列時，for 迴圈是更適合的選擇。
    - 您可以通過控制迴圈的起始值、終止條件和步進來實現對陣列的更靈活操作。
3. **do while 迴圈**：
    - 當您需要在每次迴圈結束後檢查條件，以決定是否繼續執行下一次迴圈時，do while 迴圈是一個很好的選擇。它保證至少執行一次迴圈中的代碼，然後在每次迴圈結束後檢查條件，如果條件為真，則繼續迴圈。