# Collections : Lists

---

- A flexible way to work with sets of object/values.
- Compared to arrays, the group of objects/values you work with can grow and shrink dynamically.
- A collection is a class and it requires an instance of the class before adding elements to that collection.
- For collections that only contain on data type use the `System.Collection.Generic` namespace.

### List Declaration examples

```csharp
var numbers = new List <int>(); // List of type int **without** values
var numbers = new List <int>{ 1, 5, 35, 100}; // List of type **with** values
```

### Adding and removing values

```csharp
var numbers = new List <int>();
numbers.Add(7); // Adds an integer with a value of 7 to our list
number.Remove(7); // Removes an element with a value of 7 from our list

int index = 0;
numbers,RemoveAt(index); // Remove an element at a specific position (index)
```

### Getting a value

```csharp
var numbers =  new List <int>();
numbers.Add(25); // Adds an integer with a value of 25 to our list
int value = numbers[0]; // Will be 25
```

### Clearing a list

```csharp
var numbers = new list <int>();
numbers.Add(25);
numbers.Add(50);
numbers.Add(75);
numbers.Clear(); // Deletes evert element in our list
```

### List and loops

```csharp
var numbers = new list <int>{ 5, 10, 15, 20, 25, 30, 35, 40 };

foreach(int element in numbers) // foreach loop
{
		Console.WriteLine(element); 
}

foreach(int i = 0; i < numbers.**Count**; i++)
{
		console.Write(element);
}
```

### List 和一般的 array 在使用上的區別：

---

1. **彈性：**
    - List 具有動態大小，可以根據需要自動調整其大小。這意味著您可以動態添加或刪除元素，而不需要事先知道列表的大小。
    - 一般的 array 在初始化時必須指定大小，並且在運行時無法更改大小。這意味著一旦創建了一個 array，它的大小就是固定的，無法動態添加或刪除元素。
2. **記憶體佔用：**
    - List 具有自動調整大小的功能，這意味著它可能會佔用比實際元素數量更多的記憶體。這是因為 List 內部可能會維護一個比實際大小更大的內部陣列，以便在需要時擴展容量。
    - 一般的 array 在初始化時分配了固定大小的記憶體，因此它的記憶體佔用量是固定的，不會因為元素數量的變化而改變。
3. **性能：**
    - 在添加或刪除元素時，List 可能會比一般的 array 更具性能，特別是在大量操作時。這是因為 List 內部可能會使用更有效率的算法來調整大小，而不是每次都重新創建一個新的 array。
    - 一般的 array 在初始化後不支持動態大小調整，因此在需要添加或刪除元素時，可能需要創建新的 array，並將原有元素複製到新的 array 中，這可能導致性能下降。

List 提供了更多的彈性和方便性，特別是在需要動態大小的情況下。

一般的 array 則更適合在元素數量固定且需要更低記憶體開銷的情況下使用。