# Naming Convention and Coding Standard

---

```csharp
using System;

namespace test
{
    // Class names like ClientActivity
    class Program
    {
        // Methid name like CalculateValue
        static void Main(string[] args)
        {
            // local variables like itemCount
            // use userControl instead of  usrCtr
            //Don't use numbers at the start of varialble names

            // Correct
            string myName;
            int lastNum;
            bool isSaved;

            // Avoid
            // String myname;
            // Int32 lastname;
            // Boolean isSaved
        }
    }
}
```

### 參考網站 ⇒ [https://www.dofactory.com/csharp-coding-standards](https://www.dofactory.com/csharp-coding-standards)