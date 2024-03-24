# Setter & Getter

---

### Private & Public

Making member variables  private is  fundamental principle  of object-oriented programing known as encapsulation.

Encapsulation is the practice of hiding the internal state of an object  and allowing access modification  through methods ( like getters and setters).

### Why private?

**Data Integrity :** 

By making member variables private, we can control how they are access and modified.

This allow us enforce rules on how the the data is set.

For example, we can perform validation in the setter method of a property to ensure the data is always  in a valid state.

**Abstraction :** 

Making members variables private hides the internal implementation detail of the class.

This allows  us to change the internal implementation without affecting other parts  of the code that use the class. 

### Getter

```csharp
 private string _name;
 
 public void setName(string name)
        {
            _name = name == "" ? "defaultName" : name;
        }
```

### Setter

```csharp
#Car.cs

private string _name;

public string getName()
{
    return _name;
}

===============================
#Program.cs

static void Main(string[] args)
        {
            Car myCar = new Car();
            myCar.setName("my best Car");
            Console.WriteLine(myCar.getName()); =>呼叫 private _name
            myCar.Details();
        }
```