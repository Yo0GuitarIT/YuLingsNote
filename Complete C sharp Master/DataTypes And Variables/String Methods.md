# String Methods

---

String is an object of the `System.String class`.

Here in programming terms string means sequence of characters.

Functions of the String class are used to manipulate and to perform various actions on a given string.

### Various string Methods

- SubString(int32)
- ToLower()
- ToUpper()
- Trim()
- IndexOf(string)
- IsNullOrWhiteSpace

```csharp
static void Main(string[] args)
        {
            string firstName = "Dennis";
            string lastName = "Panjuta";
            string fullName = string.Concat("", firstName, lastName, "");
            Console.WriteLine(firstName.Substring(2)); //output: nnis
            Console.WriteLine(firstName[2..]); //output: nnis =>Substring替代的寫法
            Console.WriteLine(firstName.ToLower()); //output: dennis
            Console.WriteLine(firstName.ToUpper()); //output: DENNIS

            Console.WriteLine(fullName.Trim()); //output:DennisPanjuta
            Console.WriteLine(fullName.IndexOf('e')); //output:1
            Console.WriteLine(String.IsNullOrWhiteSpace(firstName)); //output:false
        }
```

### String.Format Explained

- In C# the `String.Format` method is used to insert the object or variable value inside any string.
- With the `String.Format` we can replace the value in the specified format.
- Syntax: `String.Format`(”any string{index}”,object;

```csharp
var name = "Denis";
Console.WriteLine(String.Format("My name is {0}.", name));
// Here the string name will be replace at Index{0} in the string
// Output => My name is Denis.
```

*⇒ 在 C# 中，可以使用 `var` 關鍵字來宣告變數。`var` 是一種隱含型別，意味著編譯器會根據賦值運算式的型別來自動推斷變數的型別。*