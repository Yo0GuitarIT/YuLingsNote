# Abstract "as" & "is" Keyword

延續上一份程式碼，在 Program.cs 新增以下資訊

```csharp
namespace AbstractClassesC
{
    class Program
    {
        static void Main(string[] arg)
        {
            Shape[] shapes = { new Cube(2), new Sphere(3) };

            foreach (Shape shape in shapes)
            {
                shape.GetInfo();

                Cube? iceCube = shape as Cube;
                if (iceCube == null)
                {
                    Console.WriteLine("This Shape is no Cube");
                }
                if (iceCube is Cube)
                {
                    Console.WriteLine("This Shape a Cube");
                }
            }

            object cub1 = new Cube(7);
            Cube cub2 = (Cube)cub1;
            Console.WriteLine(
                "{0} has a Volume of {1}",
                cub2.Name,
                cub2.Volume());
        }
    }
}
```

## 說明

1. **`as` 關鍵字**：

   - `as` 關鍵字用於進行安全的類型轉換。當你有一個父類型的實例，但你想要將其轉換為子類型時，你可以使用 `as` 關鍵字。

   - 在這段程式碼中，我們先將 `shape` 變數轉換為 `Cube` 類型的實例，使用 `shape as Cube`。這樣做是為了方便後續的操作，因為 `Cube` 是 `Shape` 的子類型，所以可以安全地進行這種轉換。

   - 如果轉換成功，`iceCube` 變數將會存儲轉換後的 `Cube` 實例；如果轉換失敗（即 `shape` 不是 `Cube` 的實例），則 `iceCube` 將會是 `null`。

   - 在程式碼中，我們使用 `if (iceCube == null)` 來檢查轉換是否成功。如果 `iceCube` 是 `null`，則表示轉換失敗，這意味著 `shape` 不是 `Cube`。

2. **`is` 關鍵字**：

   - `is` 關鍵字用於檢查一個物件是否是特定類型的實例。它返回一個布林值，指示給定物件是否是指定類型的實例。

   - 在這段程式碼中，我們使用 `if (iceCube is Cube)` 來檢查 `iceCube` 變數是否是 `Cube` 類型的實例。

   - 如果 `iceCube` 是 `Cube` 類型的實例，條件式將會成立，並且程式碼將會執行 `Console.WriteLine("This Shape a Cube");`，表示這個形狀是一個立方體。

總結來說，`as` 用於安全的類型轉換，而 `is` 用於檢查一個物件是否是特定類型的實例。
在程式碼中，這兩個關鍵字一起使用，以確定給定物件的類型並進行相應的操作。
