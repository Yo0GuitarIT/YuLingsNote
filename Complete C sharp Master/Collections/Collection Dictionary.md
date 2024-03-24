# Collection : Dictionary

---

```csharp
   Dictionary <int, string> myDictionary = new Dictionary<int, string>()
            {
                { 1, "one" },
                { 2, "two" },
                { 3, "three" },
            };
```

1.

```csharp
namespace DictionariesDemo
{
    class Program
    {
        // key - value
        // Auro - car
        static void Main(string[] args)
        {
            Employee[] employees =
            {
                new Employee("CEO", "Gwyn", 95, 200),
                new Employee("Manager", "Joe", 35, 25),
                new Employee("HR", "Lora", 32, 21),
                new Employee("Secretary", "Petra", 28, 18),
                new Employee("Intern", "Ernest", 22, 8),
            };

            Dictionary<string, Employee> employeeDirectoy = new Dictionary<string, Employee>();
            foreach (Employee people in employees)
            {
                employeeDirectoy.Add(people.Role, people);
            }

            **string key = "CEO";
            if (employeeDirectoy.ContainsKey(key))
            {
                Employee empl = employeeDirectoy[key];
                Console.WriteLine("Employee Name : {0}", empl.Name);
                Console.WriteLine("Employee Role : {0}", empl.Role);
                Console.WriteLine("Employee Salary : {0}", empl.Salary);
            }
            else
            {
                Console.WriteLine("No employee found with this key {0}", key);
            }
        }**
    }

    class Employee
    {
        // few properties like Role Name, Age and Rate.
        public string Role { get; set; }
        public string Name { get; set; }
        public int Age { get; set; }
        public float Rate { get; set; }

        // Yearly Salary = rate/h * number od days * number of weeks * number od months
        public float Salary
        {
            get { return Rate * 8 * 5 * 4 * 12; }
        }

        // simple constructor
        public Employee(string role, string name, int age, float rate)
        {
            this.Role = role;
            this.Name = name;
            this.Age = age;
            this.Rate = rate;
        }
    }
}

```

1. use `TryGetValue`

```csharp
namespace DictionariesDemo
{
    class Program
    {
        // key - value
        // Auro - car
        static void Main(string[] args)
        {
            Employee[] employees =
            {
                new Employee("CEO", "Gwyn", 95, 200),
                new Employee("Manager", "Joe", 35, 25),
                new Employee("HR", "Lora", 32, 21),
                new Employee("Secretary", "Petra", 28, 18),
                new Employee("Intern", "Ernest", 22, 8),
            };

            Dictionary<string, Employee> employeeDirectoy = new Dictionary<string, Employee>();
            foreach (Employee people in employees)
            {
                employeeDirectoy.Add(people.Role, people);
            }

            **Employee result = null;
            // using TryGetValue() it returns true if the operation was successful and false otherwise
            if (employeeDirectoy.TryGetValue("Intern", out result))
            {
                Console.WriteLine("Value Restrieved!.");

                Console.WriteLine("Employee Name : {0}", result.Name);
                Console.WriteLine("Employee Role : {0}", result.Role);
                Console.WriteLine("Employee Age : {0}", result.Age);
                Console.WriteLine("Employee Salary : {0}", result.Salary);
            }
            else
            {
                Console.WriteLine("The key does not exist");
            }**
        }
    }

    class Employee
    {
        // few properties like Role Name, Age and Rate.
        public string Role { get; set; }
        public string Name { get; set; }
        public int Age { get; set; }
        public float Rate { get; set; }

        // Yearly Salary = rate/h * number od days * number of weeks * number od months
        public float Salary
        {
            get { return Rate * 8 * 5 * 4 * 12; }
        }

        // simple constructor
        public Employee(string role, string name, int age, float rate)
        {
            this.Role = role;
            this.Name = name;
            this.Age = age;
            this.Rate = rate;
        }
    }
}
```

1. use `ElementAt(i)`

```csharp
namespace DictionariesDemo
{
    class Program
    {
        // key - value
        // Auro - car
        static void Main(string[] args)
        {
            Employee[] employees =
            {
                new Employee("CEO", "Gwyn", 95, 200),
                new Employee("Manager", "Joe", 35, 25),
                new Employee("HR", "Lora", 32, 21),
                new Employee("Secretary", "Petra", 28, 18),
                new Employee("Intern", "Ernest", 22, 8),
            };

            Dictionary<string, Employee> employeeDirectoy = new Dictionary<string, Employee>();
            foreach (Employee people in employees)
            {
                employeeDirectoy.Add(people.Role, people);
            }

            **for (int i = 0; i < employeeDirectoy.Count; i++)
            {
                // using ElementAt(i) to return the key-value pair stored at index i
                KeyValuePair<string, Employee> keyValuePair = employeeDirectoy.ElementAt(i);
                // print the key
                Console.WriteLine("Key: {0}", keyValuePair.Key);
                // Storing the properties of the employee object
                Employee employeeValue = keyValuePair.Value;
                // Print the properties of the employee object
                Console.WriteLine("Employee Name: {0}", employeeValue.Name);
                Console.WriteLine("Employee Role: {0}", employeeValue.Role);
                Console.WriteLine("Employee Age: {0}", employeeValue.Age);
                Console.WriteLine("Employee Salary: {0}\n", employeeValue.Salary);
            }**
        }
    }

    class Employee
    {
        // few properties like Role Name, Age and Rate.
        public string Role { get; set; }
        public string Name { get; set; }
        public int Age { get; set; }
        public float Rate { get; set; }

        // Yearly Salary = rate/h * number od days * number of weeks * number od months
        public float Salary
        {
            get { return Rate * 8 * 5 * 4 * 12; }
        }

        // simple constructor
        public Employee(string role, string name, int age, float rate)
        {
            this.Role = role;
            this.Name = name;
            this.Age = age;
            this.Rate = rate;
        }
    }
}

```