# Public

---

The `public` keyword is an access modifier for types and type members. 

Public access is the most permissive access level.

In the following example, two classes are declared, `PointTest` and `Program`. The public members `x` and `y` of `PointTest` are accessed directly from `Program`.

```csharp
class PointTest
{
    public int x;
    public int y;
}

class Program
{
    static void Main()
    {
        var p = new PointTest();
        // Direct access to public members.
        p.x = 10;
        p.y = 15;
        Console.WriteLine($"x = {p.x}, y = {p.y}");
    }
}
// Output: x = 10, y = 15
```

If you change the `public` access level to [private](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/private) or [protected](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/protected), you will get the error message:

'PointTest.y' is inaccessible due to its protection level.