# Why would we use Params?

---

在C#中，`params` 關鍵字允許您在方法中聲明一個具有可變數量參數的參數陣列。

在調用方法時傳遞任意數量的參數，而不需要手動建立陣列。

以下是一些使用 `params` 的優缺點以及需要注意的部分：

### 優點：

1. **彈性：** `params` 參數提供了彈性，允許方法接受可變數量的參數，從而簡化了方法的使用。
2. **簡化調用：** 使用 `params` 參數可以簡化方法的調用，因為您不需要手動建立陣列來傳遞多個參數。

### 缺點：

1. **效能：** 在傳遞大量參數時，使用 `params` 可能會導致效能問題，因為每次調用方法時都會創建一個新的陣列。這可能會導致額外的記憶體開銷和執行時間。
2. **可讀性：** 使用 `params` 可能會降低代碼的可讀性，因為不清楚方法的確切參數數量。

### 注意事項：

1. **過度使用：** 避免在每個方法中都使用 `params`。它應該僅用於接受可變數量參數的情況下，而不是作為一個通用的替代方案。
2. **效能考量：** 在性能敏感的應用中，請考慮使用明確的參數列表而不是 `params`，以避免不必要的陣列分配和記憶體開銷。
3. **參數順序：** 如果方法聲明了多個參數，其中一個是 `params`，請確保它是方法簽名中的最後一個參數，因為它將吸收所有剩餘的參數。

```csharp
using System.Runtime.ConstrainedExecution;

namespace ParaExample
{
    class Program
    {
        static void Main(string[] args)
        {
            int sum1 = Sum(1, 2, 3);
            int sum2 = Sum(4, 5, 6, 7, 8);
            int sum3 = Sum();

            Console.WriteLine(sum1);
            Console.WriteLine(sum2);
            Console.WriteLine(sum3);
        }

        // Declare a method that uses the "params" keyword
        public static int Sum(params int[] numbers)
        {
            int total = 0;
            foreach (int number in numbers)
            {
                total += number;
            }

            return total;
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
            double average1 = Average(1, 2, 3);
            double average2 = Average(4, 5, 6, 7, 8);
            double average3 = Average();

            Console.WriteLine(average1);
            Console.WriteLine(average2);
            Console.WriteLine(average3);
        }

        // Declare a method that uses the "params" keyword
        // Calcuates the average
        public static double Average(params int[] numbers)
        {
            int total = 0;
            int count = 0;
            foreach (int number in numbers)
            {
                total += number;
                count++;
            }
            double result = (double)total / count;
            return result;
        }
    }
}
```