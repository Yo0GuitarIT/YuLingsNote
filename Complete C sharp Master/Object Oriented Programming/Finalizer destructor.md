# Finalizer / destructor

---

**簡介**

C# 中的 finalizer（也稱為 destructor）是一種特殊方法，用於在物件被垃圾回收器回收之前執行清理程式碼。

## **語法**

finalizer 的語法如下：

```csharp
~class_name() {
  // 清理程式碼
}
```

其中：

- `~` 是 finalizer 的標誌。
- `class_name` 是類別的名稱。

## **使用 finalizer**

finalizer 可以用於以下用途：

- 釋放非託管資源。
- 執行物件終止時的清理邏輯。

## **例子**

以下是一個使用 finalizer 來釋放非託管資源的例子：

```csharp
public class MyClass {
  private IntPtr unmanagedResource;

  public MyClass() {
    unmanagedResource = Marshal.AllocHGlobal(1024);
  }

  ~MyClass() {
    Marshal.FreeHGlobal(unmanagedResource);
  }
}
```

這個例子中，`MyClass` 類別使用 `Marshal.AllocHGlobal()` 方法分配非託管記憶體。`MyClass` 類別的 finalizer 會使用 `Marshal.FreeHGlobal()` 方法釋放非託管記憶體。

以下是一個使用 finalizer 來執行物件終止時的清理邏輯的例子：

```csharp
public class MyClass {
  private FileStream fileStream;

  public MyClass(string fileName) {
    fileStream = new FileStream(fileName, FileMode.OpenOrCreate);
  }

  ~MyClass() {
    fileStream.Close();
  }
}
```

這個例子中，`MyClass` 類別使用 `FileStream` 物件來開啟檔案。`MyClass` 類別的 finalizer 會關閉檔案。

## **注意事項**

使用 finalizer 時需要注意以下事項：

- finalizer 的執行時機是不確定的。
- finalizer 可能不會被執行。
- finalizer 會降低效能。

因此，應儘量避免使用 finalizer。如果需要使用 finalizer，應注意上述事項。

## **參考資源**

- C# Finalizers - Microsoft Docs: [https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/finalizers](https://docs.microsoft.com/en-us/dotnet%3C/0%3E/csharp/programming-guide/classes-and-structs/finalizers)