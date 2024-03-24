# Process of storing data in a variable

Variables

- Type
- Name
- Data

```csharp
int iAmaANumber = 5;
float pi = 3.1415;
bool isGPSEnabled = true;
string myName = "Dennis";
char at = '@';
```

---

```csharp
public class Lecture{
	int age =15;  // This is a variable of type integer
	public static void Main(string[] args){
		Console.WriteLine(age); //Output will be 15;
	}
}
```

```csharp
public class Lecture{
	int age = 15;
	public static void Main(string[] args){
		age = 20;
		Console.WriteLine(age); //Output will be 20
	}
}
```

```csharp
public class Lecture{
	int age; // default value assigned = 0
	public static void Main(string[] args){
		age = 20;
		Console.WriteLine(age); //Output will be 0
	}
}
```

```csharp
public class Lecture{
	public static void Main(string[] args){
		// Creating the variable inside of the Method
		// The variable can only get used inside of the method
		int age = 15;
		Console.WriteLine(age); //Output will be 0
	}
}
```
