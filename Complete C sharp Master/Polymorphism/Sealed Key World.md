# Sealed Key World

在C#中，`sealed` 關鍵字用於阻止類別被繼承，作用範圍 **`class`** , **`property`**, **`method`**。

聲明父層為 `sealed` 時，它將不能被其他類別繼承。

使用 `sealed` 關鍵字可以提供以下功能：

1. 防止類別被擴展：有時候你可能希望某個類別的行為不能被修改或擴展，這時你可以將該類別聲明為 **`sealed`**，這樣其他類別就不能再繼承它，從而保證了這個類別的行為不會被改變。

2. 優化性能：在C#中，如果你知道某個類別不需要被繼承，可以將它聲明為 **`sealed`**，這樣編譯器在生成代碼時可以進行一些優化，提高性能。

3. 安全性：有時你可能希望某個類別的特定功能或行為不能被修改，這時可以將它聲明為 **`sealed`**，以防止其他開發者對這個類別進行擴展或修改，從而提高代碼的安全性。

`sealed` 關鍵字用於限制類別的繼承，提供了更加靈活的代碼設計和更高的代碼安全

## Example
``` csharp

namespace PolymorphismC
{
    class BMW : Car
    {
        private string brand = "BMW";
        public string Model { get; set; }

        public BMW(int hp, string color, string model)
            : base(hp, color)
        {
            this.Model = model;
        }

        public new void ShowDetails()
        {
            Console.WriteLine($"Brand : {brand}, HP : {HP}, Color : {Color}");
        }

        public sealed override void Repair() //sealed註記method
        {
            Console.WriteLine($"The {brand} {Model} is repaired!");
        }
    }



    sealed class M3 : BMW // sealed註記類別
    {
        public M3(int hp, string color, string model)
            : base(hp, color, model) { }

        // 無法被繼承使用
        /* public override void Repair() 
        { 
            base.Repair(); 
        } */  
    }
   
   
   // 無法繼承M3
    /* class D2 : M3 
    { 
        public D2(int hp, string color, string model) 
             : base(hp, color, model) { } 
    } */


}


```
