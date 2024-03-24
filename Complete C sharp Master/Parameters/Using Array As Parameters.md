# Using Array As Parameters

---

在 C# 中，陣列是一種引用類型。

這表示陣列變數實際上是指向陣列底層資料的參考。

當您將陣列作為參數傳遞給方法時，您實際上是在傳遞對該陣列的地址。

方法可以對陣列進行修改，這些修改將反映在呼叫方中的原始陣列中。

這是因為方法接收的是對陣列的引用，因此它可以對陣列底層資料進行直接修改。

在 C# 中將陣列作為參數傳遞給方法：

```csharp
// 宣告一個陣列
int[] numbers = new int[] { 1, 2, 3, 4, 5 };

// 將陣列傳遞給方法
PrintArray(numbers);

// 方法修改陣列
void PrintArray(int[] array)
{
  for (int i = 0; i < array.Length; i++)
  {
    array[i] = array[i] * 2;
  }
}
```

`PrintArray()` 方法會將陣列中的每個元素乘以 2。這些修改將反映在呼叫方中的原始陣列中。

以下是一些在 C# 中將陣列作為參數傳遞給方法的優點：

- 它允許您將大量資料傳遞給方法。
- 它允許方法修改陣列中的資料。
- 它可以提高程式碼的可讀性和可維護性。

在 C# 中將陣列作為參數傳遞給方法也有一些缺點：

- 它可能會導致意外修改陣列。
- 它可能會使程式碼難以理解。

```csharp
using System.Runtime.ConstrainedExecution;

namespace arrayAsParameters
{
    class Program
    {
        static void Main(string[] args)
        {
        int[] studentsGrades = new int[] { 15, 13, 8, 12, 6, 16 };
        double averageResult = GetAverage(studentsGrades);

        foreach (int grade in studentsGrades)
        {
            Console.WriteLine("Grade : " + grade);
        }

        Console.WriteLine($"The average is {averageResult}");

        }

        static double GetAverage(int[] gradesArray)
        {
            int size = gradesArray.Length;
            double average;
            int sum = 0;

            for (int i = 0; i < size; i++)
            {
                sum += gradesArray[i];
            }

            average = (double)sum / size;
            return average;
        }
    }
}

```

```csharp
using System.Runtime.ConstrainedExecution;

namespace arrayAsParameters
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] happiness = new int[] { 1, 2, 3, 4, 5 };
            int[] newHappiness = Increase(happiness);
            foreach (int newValue in newHappiness)
            {
                Console.WriteLine(newValue);
            }
        }

        static int[] Increase(int[] valueArray)
        {
            for (int i = 0; i < valueArray.Length; i++)
            {
                valueArray[i] += 2;
            }
            return valueArray;
        }
    }
}
```