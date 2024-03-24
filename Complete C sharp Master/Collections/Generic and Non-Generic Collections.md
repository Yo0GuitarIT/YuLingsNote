# Generic and Non-Generic Collections

---

### What is a Collection?

- Collections are classes that we can use to store a collection objects.
- Not limit to one type of objects.
- No size constraints, It can grow in size as we add more elements.

### Why do we need Collections?

- We use them to store, manage and manipulate groups of objects more efficiently.
    - Adding
    - Deleting
    - Replacing
    - Searching
    - Copying

### -Non-Generic

Can store any type of objects

**Located in ⇒** `System.Collections namespace`

```csharp
int num1 = 5;
float num2 = 3.14f;
string name = "Denis";

ArrayList myArrayList = new ArratList();

myArrayList.Add(num1);
myArrayList.Add(num2);
myArrayList.Add(num3);

foreach(object element in myArrayList)
{
	Console.Write(element + " ");
}

// 5 3.14 Denis
```

### -Generic

limited to one type of objects

**Located in ⇒** `System.Collection.Generic namespace`

```csharp
string animal1 = "Cat";
string animal2 = "Dog";
string animal3 = "Flamingo";

List <string> myList = new List<string>();

```