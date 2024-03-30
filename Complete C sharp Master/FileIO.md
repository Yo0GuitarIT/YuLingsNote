# Reading & Writing Text

### Reading

_使用 `File.ReadAllText` 和 `File.ReadAllLines` 方法來讀取文本檔案的內容，並將其輸出到控制台。_

- Code

```csharp
using System;

namespace FileIOC
{
    class Program
    {
        static void Main(string[] args)
        {
            string textUrl = "./text.txt";

            // Example 1 Reading Text
            string text = System.IO.File.ReadAllText(textUrl);
            Console.WriteLine("Textfile contains following text : {0}", text);

            string[] lines = System.IO.File.ReadAllLines(textUrl);
            Console.WriteLine("Textfile contains following text: ");
            foreach (string line in lines)
            {
                Console.WriteLine("\t" + line);
            }
        }
    }
}
```

在 C#中讀取文本檔案的兩種方式：`File.ReadAllText` 和 `File.ReadAllLines`。

1. **`File.ReadAllText`**：

   - `File.ReadAllText` 方法用於讀取文本檔案的全部內容並將其作為一個字符串返回。
   - 在程式碼中，使用 `File.ReadAllText(textUrl)` 從指定的檔案路徑 `textUrl` 中讀取文本內容。
   - 讀取後的文本內容被存儲在 `text` 變數中，然後使用 `Console.WriteLine` 將其輸出到控制台。

2. **`File.ReadAllLines`**：
   - `File.ReadAllLines` 方法用於將文本檔案的所有行讀取為字符串陣列。
   - 在程式碼中，使用 `File.ReadAllLines(textUrl)` 從指定的檔案路徑 `textUrl` 中讀取所有行。
   - 讀取後的每一行文本被存儲在 `lines` 陣列中，然後使用 `foreach` 迴圈逐行輸出到控制台。

### Writing

- code

```csharp
// using System.IO.File

using System.Net;

namespace FileIOC
{
    class Program
    {
        static void Main(string[] args)
        {
            // Writing text

            // method 1
            string[] lines = { "first 91", "second 89", "third 93" };
            File.WriteAllLines("./highScores.txt", lines);

            // method 2
            Console.WriteLine("Please give the file a name:");
            string? fileName = Console.ReadLine();
            Console.WriteLine("Please enter the text for the file:");
            string? input = Console.ReadLine();
            File.WriteAllText($"./{fileName}.txt", input);

            // method 3
            using (StreamWriter file = new StreamWriter("./myText2.txt"))
                foreach (string line in lines)
                {
                    if (line.Contains('9'))
                    {
                        file.WriteLine(line);
                    }
                }

            using (StreamWriter file2 = new StreamWriter("./myText2.txt", true))
                file2.WriteLine("Add");
        }
    }
}
```

1. **`File.WriteAllLines` 方法：**

   - 使用此方法可以將字串陣列中的每一行文字寫入檔案中。
   - 在這個例子中，字串陣列 `lines` 包含三行文字，分別是 "first 91"、"second 89" 和 "third 93"。
   - `File.WriteAllLines` 方法會將這些文字寫入檔案 "highScores.txt" 中。

2. **使用者輸入：**

   - 使用者可以自行輸入檔案名稱和要寫入的文字內容。
   - `Console.ReadLine()` 用於接收使用者的輸入，分別用於設定檔案名稱和文字內容。
   - 使用者輸入的檔案名稱將會加上 ".txt" 副檔名，並寫入到當前目錄下。

3. **`StreamWriter`：**
   - 使用 `StreamWriter` 類別可以更靈活地控制檔案的寫入操作。
   - 在這個例子中，程式透過 `StreamWriter` 將文字寫入到 "myText2.txt" 檔案中。
   - 第一個 `StreamWriter` 實例是使用 `using` 陳述式，它會自動關閉檔案流，確保資源釋放。
   - 使用 `foreach` 迴圈遍歷 `lines` 陣列中的每一行文字，如果文字中包含數字 '9'，則將該行寫入檔案。
   - **第二個 `StreamWriter` 實例使用 `true` 參數初始化，這表示它會將文字附加到現有的檔案內容之後，而不是覆蓋原有內容。**

### Note：

- 這些方法提供了多種方式來將文字寫入到檔案中，使用者可以根據需求選擇適合的方法。
- `File.WriteAllLines` 和 `File.WriteAllText` 是簡單直觀的方法，適用於快速寫入少量文字。
- `StreamWriter` 提供了更多控制選項，例如逐行寫入、追加模式等，適用於處理更複雜的寫入需求。
- **使用 `using` 陳述式來管理檔案流的生命週期，確保資源在使用完畢後被正確釋放，避免資源洩漏和記憶體洩漏問題。**
