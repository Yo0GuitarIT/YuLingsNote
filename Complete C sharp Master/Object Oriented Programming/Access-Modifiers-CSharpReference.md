# Access Modifiers (C# Reference)

---

| Caller's location                      | public | protected internal | protected | internal | private protected | private |
| -------------------------------------- | ------ | ------------------ | --------- | -------- | ----------------- | ------- |
| Within the class                       | ✔️️    | ✔️                 | ✔️        | ✔️       | ✔️                | ✔️      |
| Derived class (same assembly)          | ✔️     | ✔️                 | ✔️        | ✔️       | ✔️                | ❌      |
| Non-derived class (same assembly)      | ✔️     | ✔️                 | ❌        | ✔️       | ❌                | ❌      |
| Derived class (different assembly)     | ✔️     | ✔️                 | ✔️        | ❌       | ❌                | ❌      |
| Non-derived class (different assembly) | ✔️     | ❌                 | ❌        | ❌       | ❌                | ❌      |

[Public](./Access%20Modifiers/Public.md)

[**Internal**](./Access%20Modifiers/Internal.md)

[Private](./Access%20Modifiers/Private.md)

[protect internal](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/protected-internal)

[**Protected**](./Access%20Modifiers/Protected.md)

[private protected](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/private-protected)

參考資料：

[https://code-maze.com/csharp-access-modifiers/](https://code-maze.com/csharp-access-modifiers/)

[https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/access-modifiers](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/access-modifiers)
