# Struct & Enum

在C#中，`struct` 和 `enum` 都是值類型（value type）。

1. **struct（結構）**：
    - `struct` 是一種用於定義輕量級物件的值類型。
    - 通常用於表示具有少量屬性的數據，並且它的實例直接包含數據，而不是引用。
    - 在記憶體中，`struct` 的實例通常被存儲在堆疊上。
    
    例如：
    
    ```csharp
    public struct Point
    {
        public int X;
        public int Y;
    }
    ```
    
2. **enum（列舉）**：
    - `enum` 用於定義具名整數常數的值類型。
    - 它允許你創建一組具名的整數值，這樣在代碼中使用時更具可讀性。
    - 在記憶體中，`enum` 的值通常被視為整數。
    
    例如：
    
    ```csharp
    public enum Days
    {
        Sunday,
        Monday,
        Tuesday,
        Wednesday,
        Thursday,
        Friday,
        Saturday
    }
    
    ```
    

總的來說，這兩者都是值類型，直接包含其數據，而不需要額外的引用。
