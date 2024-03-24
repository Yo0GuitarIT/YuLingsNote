# Editing And Removing Entries in a Dictionary

---

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

            **// update
            string keyToUpdate = "HR";
            if (employeeDirectoy.ContainsKey(keyToUpdate))
            {
                employeeDirectoy[keyToUpdate] = new Employee("HR", "Eleka", 26, 18);
                Console.WriteLine("Employee with Role/Key {0} was uodate!.\n", keyToUpdate);
            }
            else
            {
                // if on print an error message
                Console.WriteLine("No employee found with this key {0}.\n", keyToUpdate);
            }

            // Remove
            string KeyToRemove = "Intern";
            if (employeeDirectoy.Remove(KeyToRemove))
            {
                Console.WriteLine("Employee with Role/Key {0} was removed!\n", KeyToRemove);
            }
            else
            {
                // if on print an error message
                Console.WriteLine("No employee found with this key {0}.\n", keyToUpdate);
            }**

            for (int i = 0; i < employeeDirectoy.Count; i++)
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
            }
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