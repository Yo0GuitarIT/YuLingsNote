# Collections: ArrayLists

---

```csharp
using System.Collections;  //使用ArrayList時，需要引入

namespace ArrayListC
{
    class Program
    {
        static void Main(string[] args)
        {
            //declare an ArrayList with undefined amount of object
            ArrayList myArrayList = new ArrayList();
            //declare an ArrayList with defined amount of object
            ArrayList myArrayList2 = new ArrayList(100);

            myArrayList.Add(25);
            myArrayList.Add("Hello");
            myArrayList.Add(13.37);
            myArrayList.Add(13);
            myArrayList.Add(128);
            myArrayList.Add(25.3);
            myArrayList.Add(13);

            // delete element with specific value from the arraylist
            myArrayList.Remove(13);
            myArrayList.Remove(13);
            myArrayList.Remove(13); //沒有其他13的元素可以移除 

            //delete element with specific  position
            myArrayList.RemoveAt(0); //  remove 25

            Console.WriteLine(myArrayList.Count);

            double sum = 0;
            foreach (object obj in myArrayList)
            {
                if (obj is int)
                {
                    sum += Convert.ToDouble(obj);
                }
                else if (obj is double)
                {
                    sum += (double)obj;
                }
                else if (obj is string)
                {
                    Console.WriteLine(obj);
                }
            }
            Console.WriteLine(sum);
        }
    }
}
```

在C#中，所有的類型都直接或間接地繼承自 `System.Object` 類型。

因此 `int`、`string`、`double` 等基本類型的變數添加到集合時，它們將被自動視為 `object` 型別，因為它們都可以向上轉型為 `object`。

這是因為 `System.Object` 是所有類型的基類，所以任何類型都可以轉換為 `object` 型別。這種轉換稱為隱式轉換，它是C#語言的一個特性，稱為“隱式類型轉換”。

因此，當您將 `int`、`string`、`double` 等基本類型的變數添加到 `ArrayList` 或其他類型的集合中時，它們將被自動視為 `object` 型別的元素。

舉例來說，當您添加一個 `int` 值到 `ArrayList` 中時，實際上是將該 `int` 值轉換為 `object` 型別，然後將它添加到集合中。在迭代集合時，您可以使用 `foreach` 遍歷 `ArrayList` 中的每個元素，並將每個元素視為 `object` 型別來處理。

`int`、`string`、`double` 等基本類型都具有繼承自 `System.Object` 的特性，因此它們可以被視為 `object` 型別的變數。

---

### 使用 `is` 運算符：

- `obj is int` 和 `obj is string` 用於檢查變數 `obj` 是否是指定的類型（在這裡是 `int` 和 `string`）。
- 如果 `obj` 是指定的類型，則 `is` 運算符返回 `true`，否則返回 `false`。
- 使用 `is` 運算符可以幫助您在進行類型轉換或處理時進行類型檢查，從而確保程式碼的安全性。

### 使用 `==` 運算符：

- `==` 運算符用於比較兩個對象的值是否相等。
- 當比較的是基本數據類型（例如 `int`、`double` 等）時，比較的是它們的值。
- 當比較的是引用類型（例如 `string`、`object` 等）時，比較的是它們的引用，即它們在記憶體中的位置。
- 如果兩個對象的值或引用相等，則 `==` 運算符返回 `true`，否則返回 `false`。

### 區別：

- `is` 運算符用於類型檢查，而 `==` 運算符用於比較兩個對象的值或引用。
- `is` 運算符返回布林值（`true` 或 `false`），而 `==` 運算符根據比較的類型和值或引用返回布林值。

`is` 運算符用於類型檢查

 `==` 運算符用於比較值或引用。

在處理集合中的元素時，通常會使用 `is` 運算符來檢查元素的類型，然後根據不同的類型進行相應的處理。