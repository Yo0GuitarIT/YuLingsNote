# value type and reference type

Data types can be categorized into two categories based on how they occupy memory location.

## Value type in detail

- Store actual data directly
- Typically stored in the stack
- Include `int, float, long, double, char, bool, decimal. struct, enum`

  補充 => [Struct & Enum](./value%20type%20and%20reference%20type/Struct%20&%20Enum.md)

- Nullable versions available( int?, double?, etc.)
  - `*int?` 和 `double?` 是 C# 中的可為空值型別（nullable value types）的表示方式。在這裡，`?` 符號表示該型別是可為空的。通常，基本數據類型（如 int、double 等）不能存儲空值。但是，當你需要在一個變數中存儲數據或空值時，你可以使用可為空值型別。\*
  - _舉例來說，`int?` 可以存儲整數或空值，而不僅僅是正常的整數。同樣，`double?` 可以存儲雙精度浮點數或空值。_
  - _使用可為空值型別有助於處理那些可能缺失數據的情況，讓你能夠明確表示變數可能為空。當你需要區別一個變數是沒有被賦值還是確實為空值時，這種型別就變得很有用。_
- Can be store in heap if part of a reference type

## Reference type in detail

- `Reference type` is a variable type which instead of storing the value in memory directly, stores the memory location of the actual data.
- The variable here stores the memory reference of the data and not the data directly.
- Reference type data types are `string, class, Array` etc.
- When we copy this reference type of a data type it will just copy the memory address of the data so we will then have two variables pointing to the same data.
