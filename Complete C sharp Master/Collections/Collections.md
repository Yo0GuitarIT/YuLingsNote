# Collections

1. **List\<T>**：

   - 描述：動態陣列，允許在集合的任意位置插入、刪除和查詢元素。
   - 特點：提供了動態調整大小的能力，可以根據需要動態增加或減少元素的個數。

2. **Dictionary\<TKey, TValue>**：

   - 描述：鍵值對集合，用於存儲鍵值對映關係。
   - 特點：通過唯一的鍵來訪問值，快速查找、插入和刪除元素。

3. **Queue\<T>**：

   - 描述：先進先出（FIFO）的集合。
   - 特點：保持元素的插入順序，並且每次從集合中移除元素時，都會移除最先添加的元素。

4. **Stack\<T>**：

   - 描述：後進先出（LIFO）的集合。
   - 特點：保持元素的插入順序，但是每次從集合中移除元素時，都會移除最後添加的元素。

5. **HashSet\<T>**：

   - 描述：無序、唯一元素的集合。
   - 特點：存儲唯一的元素，並且沒有固定的順序。

6. **IEnumerable\<T>**：
   - 描述：泛型的可枚舉集合介面。
   - 特點：定義了一個方法 `GetEnumerator()`，該方法返回一個 `IEnumerator<T>` 介面的實例，用於對集合進行迭代。

這些集合類型都提供了不同的功能和特點，可以根據需要選擇適合的集合類型來處理數據。

---

[Generic and Non-Generic Collections](./Generic%20and%20Non-Generic%20Collections.md)

[Collections: ArrayLists](./Collections%20ArrayLists.md)

[Collections : Lists](./Collections%20Lists.md)

[Collection : Hashtables](./Collection%20Hashtables.md)

[Hashtable - Challenge](./Hashtable%20-%20Challenge.md)

[Collection : Dictionary](./Collection%20Dictionary.md)

[Editing And Removing Entries in a Dictionary](./Editing%20And%20Removing%20Entries%20in%20a%20Dictionary.md)
