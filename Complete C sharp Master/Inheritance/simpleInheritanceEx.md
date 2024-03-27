# Simple Inheritance Example

> parent/case class <= **Inheritance Properties** <= child class  
> child class <= **passes on** <= parent/case class

## Example

- Program.cs

```csharp
namespace InheritanceDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Radio myRadio = new Radio(false, "Sony");
            myRadio.SwitchOn();
            myRadio.ListenRadio();

            TV myTV = new TV(false, "Samsung");
            // method of base class
            myTV.SwitchOn();
            // method of child class
            myTV.WatchTV();
        }
    }
}
```

- ElectricDevice.cs

```csharp
namespace InheritanceDemo
{
    class ElectricDevice
    {
        // Parent - Base
        // boolean to detemine the state of the Electric Device
        public bool IsOn { get; set; }

        // string for the brand name of the Electric Device
        public string Brand { get; set; }

        // simple constructor
        public ElectricDevice(bool isOn, string brand)
        {
            IsOn = isOn;
            Brand = brand;
        }

        // switch on the Electric Device
        public void SwitchOn()
        {
            IsOn = true;
        }

        // switch off the Electric Device
        public void SwitchOff()
        {
            IsOn = false;
        }
    }
}
```

- Radio.cs

```csharp
namespace InheritanceDemo
{
    class Radio : ElectricDevice //繼承Electric Device 的特性
    {
        // Child class
        public Radio(bool isOn, string brand)
            : base(isOn, brand) { }

        // method to listen to the radio
        public void ListenRadio()
        {
            // first check if the radio is on
            if (IsOn)
            {
                // listen to radio
                Console.WriteLine("Listen to the Radio!");
            }
            else
            {
                // print error message
                Console.WriteLine("Radio is switch off, switch it on first");
            }
        }
    }
}
```

- TV.cs

```csharp
namespace InheritanceDemo
{
    class TV : ElectricDevice //繼承Electric Device 的特性
    {
        // simple constructor
        public TV(bool isOn, string brand)
            : base(isOn, brand) { }

        // method to watch the TV
        public void WatchTV()
        {
            // first check if the radio is on
            if (IsOn)
            {
                // watch the TV
                Console.WriteLine("watch the TV!");
            }
            else
            {
                // print error message
                Console.WriteLine("TV is switch off, switch it on first");
            }
        }
    }
}
```

## 說明

_這段程式碼展示了 C# 中繼承的基本概念和如何在子類別中重用父類別的屬性和方法。_  
以下是關於 C# 繼承的重點：

1. **繼承關係的建立**：

   - 在子類別的宣告中使用冒號 `:` 來指定它要繼承的父類別。

2. **父類別（基類別）**：

   - 定義了一個 `ElectricDevice` 類別作為父類別。
   - 這個類別有兩個屬性：`IsOn`（布林型，表示電器是否開啟）和 `Brand`（字串，表示品牌名）。
   - 有一個建構函式可以初始化這兩個屬性。
   - 包含兩個方法：`SwitchOn()` 和 `SwitchOff()` 用於開啟和關閉電器。

3. **子類別**：

   - `Radio` 和 `TV` 類別都是從 `ElectricDevice` 繼承而來。
   - 子類別可以使用 `base` 關鍵字來調用父類別的建構函式。
   - 子類別可以擴展父類別的功能，並新增自己的方法。

4. **使用繼承**：

   - 在 `Main` 方法中可以看到如何創建子類別的實例並呼叫其方法。
   - `Radio` 類別的實例可以使用 `ElectricDevice` 中的 `SwitchOn()` 方法，因為它繼承了這個方法。
   - 同樣，`TV` 類別的實例也可以使用 `ElectricDevice` 中的 `SwitchOn()` 方法。

5. **重用程式碼**：
   - 透過繼承，可以重用父類別中的屬性和方法，而不需要在每個子類別中都重新定義。
