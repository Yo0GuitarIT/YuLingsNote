# TryPrase Method

---

- Converting strings into numeric data types.
- By using the `TryParse()`method you can convert a string like “128” into a numeric data type like **int**eger.
- `TryParse()` often get used **when the user submit input.**

```csharp
static void Main(string[] args)
        {
            string numberAsString = "128";
            float parseValue;

            bool success = float.TryParse(numberAsString, out parseValue);
            // Return the boolean is true when parsing was successful

            if (success)
            {
                Console.WriteLine("Parasing Successful - number is " + parseValue);
            }
            else
            {
                Console.WriteLine("Parsing Faild");
            }
        }
```

- Parsing fails when the string can not be converted into the desired data type.

---

Parse to an `int`

| WORKS | string age = “18”; |
| --- | --- |
| FAILS | string age = “18xyx”; |

Parse to an `float`

| WORKS | float age = “18.75”; |
| --- | --- |
| FAILS | float age = “18.75xyx”; |