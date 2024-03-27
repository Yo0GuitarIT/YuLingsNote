# Interface Intro

Another way to achieve abstraction in [C#](https://www.w3schools.com/cs/cs_abstract.php), is with **interfaces**.

An interface is a completely "abstract class", which can only contain abstract **methods** and **properties** (with empty bodies):

## Example

- Program.cs

```csharp
namespace InterfaceDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Ticket t1 = new Ticket(10);
            Ticket t2 = new Ticket(10);
            Console.WriteLine(t2.Equals(t1));
        }
    }
}
```

- Ticket.cs

```csharp
namespace InterfaceDemo
{
    class Ticket : IEquatable<Ticket>
    {
        // property to store the duration of the ticket in hours
        public int DurationInHours { get; set; }

        // simple constructor
        public Ticket(int durationInHours)
        {
            DurationInHours = durationInHours;
        }

        public bool Equals(Ticket other)
        {
            return this.DurationInHours == other.DurationInHours;
        }
    }
}
```

## 說明

這段程式碼定義了兩個類別：`Ticket` 和 `Program`，位於 `InterfaceDemo` 命名空間中。

**Ticket 類別**

- **實作 IEquatable<Ticket>**：這行指示 `Ticket` 類別符合 `IEquatable<Ticket>` 介面的要求。此介面確保類別具有用於物件比較的 `Equals` 方法。
- **屬性**
  - `DurationInHours` (公開)：此屬性儲存車票的持續時間（以小時為單位），允許讀取和修改其值。
- **建構函式**
  - `Ticket(int durationInHours)`：此建構函式建立一個新的 `Ticket` 物件，其持續時間為指定的小時數。
- **Equals 方法**
  - `public bool Equals(Ticket other)`：此方法實作 `IEquatable<Ticket>` 介面要求的 `Equals` 方法。它接受另一個 `Ticket` 物件 (`other`) 作為參數，並返回：
    - `true`：如果兩個 `Ticket` 物件的 `DurationInHours` 相等。
    - `false`：如果物件的 `DurationInHours` 不同。

**Program 類別**

- **Main 方法**
  - `static void Main(string[] args)`：這是程式的進入點。
  - `Ticket t1 = new Ticket(10);`: 建立一個新的 `Ticket` 物件 `t1`，持續時間為 10 小時。
  - `Ticket t2 = new Ticket(10);`: 建立另一個 `Ticket` 物件 `t2`，持續時間也為 10 小時。
  - `Console.WriteLine(t2.Equals(t1));`: 呼叫 `t2` 上的 `Equals` 方法將其與 `t1` 進行比較。然後將結果（`true` 或 `false`）列印到控制台。

**程式碼功能**

- 這段程式碼演示了如何實作 `IEquatable<Ticket>` 介面來定義自訂邏輯以比較 `Ticket` 物件。
- 比較僅根據 `DurationInHours` 屬性進行。
- `Main` 方法建立兩個持續時間相同的車票，並使用 `Equals` 方法檢查它們是否相等，該方法很可能會將 `true` 列印到控制台。

**結論**

這段程式碼展示了 C# 中介面的用法。介面可讓您定義物件的行為，而無需指定物件的實作方式。這可讓您提高程式碼的靈活性。

## 補充

### `IEquatable<Ticket>`和一般`IEquatable<T>` 的差異:

- IEquatable<Ticket> 和一般 IEquatable<T> 的主要差異在於，IEquatable<Ticket> 專門用於比較 Ticket 物件，而 IEquatable<T> 可用於比較任何類型的物件。
- IEquatable<Ticket>:
  這是個**非泛型介面**，定義了一個方法，Equals(Ticket other)。
  此方法接受另一個 Ticket 物件作為參數，並在兩個物件相等時傳回 true，否則傳回 false。
  此介面通常用於根據特定屬性或條件比較兩個相同類型的物件。
- IEquatable<T>:
  這是個**泛型介面**，定義了一個方法，Equals(T other)。
  此方法接受 T 型別的物件作為參數，並在兩個物件相等時傳回 true，否則傳回 false。
  此介面更通用，可用於比較任何類型的物件。
