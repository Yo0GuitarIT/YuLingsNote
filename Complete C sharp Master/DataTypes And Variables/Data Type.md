# Data Type

### What is byte?

`byte` 是一種基本的資料型別，用來表示 8 位元組（8 個二進制位元）。在許多程式語言中，包括 C#和 Java 等，`byte` 通常用來表示二進制數據的最小單位。

```csharp
// 00000000 = 0
// 00000001 = 1
// 00000010 = 2
// 00000011 = 3
// 00000100 = 4
// 00000101 = 5
// 00000110 = 6
// 00000111 = 7
// 00001000 = 8
```

---

1. **byte (無符號)**:

   - 占用位元組數：1 byte
   - 范圍：0 到 255

   ```csharp
   // 1 byte (8 bit) unsigned, where signed means it can be negative
   byte myByte = 255;
   byte mySecondByte = 0;
   ```

2. **sbyte (有符號)**:

   - 占用位元組數：1 byte
   - 范圍：-128 到 127

   ```csharp
   // 1 byte (8 bit) signed, where signed means it can be negative
   sbyte mySbyte = 127;
   sbyte mySecondSbyte = -128;
   ```

3. **short (有符號和無符號)**:

   - 占用位元組數：2 bytes
   - 有符號范圍：-32768 到 32767
   - 無符號范圍：0 到 65535

   ```csharp
   // 2 byte (16 bit) signed, where signed means it can be negative
   short myShort = -32768;

   // 2 byte (16 bit) unsigned, where signed means it can be negative
   ushort myUshort = 65535;
   ```

4. **int (有符號和無符號)**:

   - 占用位元組數：4 bytes
   - 有符號范圍：-2,147,483,648 到 2,147,483,647
   - 無符號范圍：0 到 4,294,967,295

   ```csharp
   // 4 byte (32 bit) signed, where signed means it can be negative
   int myInt = 2147483647;
   int mySecondInt = -2147483648;
   ```

5. **long (有符號和無符號)**:

   - 占用位元組數：8 bytes
   - 有符號范圍：-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807
   - 無符號范圍：0 到 18,446,744,073,709,551,615

   ```csharp
   // 8 byte (64 bit) signed, where signed means it can be negative
   long myLong = -9223372036854775808;
   ```

6. **float**:

   - 占用位元組數：4 bytes
   - 精度：約 7 位十進制數字

   ```csharp
   // 4 byte (32 bit) floating point number
   float myFloat = 0.751f;
   float mySecondFloat = 0.75f;
   ```

7. **double**:

   - 占用位元組數：8 bytes
   - 精度：約 15-16 位十進制數字
   - 是否要特別寫 **`d`** 取決於你的代碼風格和個人偏好。在大多數情況下，省略 **`d`** 也是可以的。

   ```csharp
   // 8 byte (64 bit) floating point number
   double myDouble = 0.751;
   double mySecondDouble = 0.75d;
   ```

8. **decimal**:

   - 占用位元組數：16 bytes
   - 精度：約 28-29 位十進制數字

   ```csharp
   // 16 byte (128 bit) floating point number
   decimal myDecimal = 0.751m;
   decimal mySecondDecimal = 0.75m;
   ```

---

有符號（signed）和無符號（unsigned）的數據類型之間的區別在於它們能夠表示的數值範圍。讓我們以 **`short`** 和 **`ushort`** 為例進行說明：

1. **有符號 (`short`)**:
   - **`short`** 可以表示正數和負數，範圍是 -32768 到 32767。

```csharp
csharpCopy code
short signedNumber = -1000;
```

1. **無符號 (`ushort`)**:
   - **`ushort`** 只能表示非負數（即正數），範圍是 0 到 65535。

```csharp
csharpCopy code
ushort unsignedNumber = 5000;
```

使用有符號或無符號取決於你的數據範圍和應用需求。

通常情況下，如果你知道數值不會是負數，你可以使用無符號數據類型以擴展可表示的正數範圍。如果需要表示正數和負數，則使用有符號數據類型。

例如，如果你在表示年齡時，不應該有負數，那麼使用 **`ushort`** 是合理的。而對於表示溫度，可能需要有負數的範圍，因此 **`short`** 是更合適的選擇。

總之，選擇有符號或無符號取決於你的數據範圍和應用場景。

---

### Char & String

1. **`char`（字符）**:
   - `char` 用於表示單個字符。
   - 占用位元組數：2 bytes
   - 例子：
     ```csharp
     char myChar = 'A';
     ```
   - 注意字符用單引號括起來，而不是雙引號。
2. **`string`（字符串）**:
   - `string` 用於表示一系列字符，即字符串。
   - 占用位元組數：取決於字符串的長度，**每個字符一般占用 2 bytes**。
   - 例子：
     ```csharp
     string myString = "Hello, World!";
     ```
   - 字符串用雙引號括起來。
   -

`char` 是用於表示單個字符，而 `string` 用於表示一系列字符，即文本。在實際應用中，`string` 更常用，因為它更靈活，能夠存儲任意長度的文本。

---

### Boolean

`bool`（布林）是 C# 中用來表示布林值的數據類型，它只有兩個可能的值：`true`（真）和`false`（假）。

以下是 `bool` 的基本特性：

- **bool（布林）**:
  - 占用位元組數：1 byte
  - 值：`true` 或 `false`
  - 例子：
    ```csharp
    bool isTrue = true;
    bool isFalse = false;
    ```

`bool` 通常用於控制流程和條件判斷，例如在 `if` 陳述句中。這使得代碼能夠根據某個條件的真假來執行不同的程式邏輯。

```csharp
bool isSunny = true;

if (isSunny)
{
    Console.WriteLine("It's a sunny day!");
}
else
{
    Console.WriteLine("It's not sunny today.");
}
```
