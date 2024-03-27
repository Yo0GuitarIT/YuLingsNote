# Inheritance Chellange 2 - Employee, Boss, Triainees

- Program.cs

```csharp
namespace inheritanceChallenge
{
    class Program
    {
        static void Main(string[] args)
        {
            Employee micheal = new Employee("Micheal", "Miller", 40000);
            micheal.Work();
            micheal.Pause();

            Boss chuckNorris = new Boss("Norris", "Chuck", 999999999, "Ferrari");
            chuckNorris.Lead();

            Trainee michelle = new Trainee("michelle", "Gartner", 10000, 32, 8);
            michelle.Learn();
            michelle.Work();
        }
    }
}
```

- Employee.cs

```csharp
namespace inheritanceChallenge
{
    class Employee
    {
        public string Name { get; set; }
        public string FirstName { get; set; }
        public int Salary { get; set; }

        public Employee(string name, string firstName, int salary)
        {
            this.Name = name;
            this.FirstName = firstName;
            this.Salary = salary;
        }

        public Employee()
        {
            Name = "Pajuta";
            FirstName = "Dennis";
            Salary = 50000;
        }

        public virtual void Work()
        {
            Console.WriteLine($"{Name} is working");
        }

        public void Pause()
        {
            Console.WriteLine($"{Name} is having a break");
        }
    }
}
```

- Boss.cs

```csharp
namespace inheritanceChallenge
{
    class Boss : Employee
    {
        public string CompanyCar { get; set; }

        public Boss(string name, string firstName, int salary, string companyCar)
            : base(name, firstName, salary)
        {
            this.CompanyCar = companyCar;
        }

        public void Lead()
        {
            Console.WriteLine("I'm a Boss!, My name is {0} {1}", Name, FirstName);
        }
    }
}
```

- Trainee.cs

```csharp
namespace inheritanceChallenge
{
    class Trainee : Employee
    {
        public int WorkingHours { get; set; }
        public int SchoolHours { get; set; }

        public Trainee(string name, string firstName, int salary, int workingHours, int schoolHours)
            : base(name, firstName, salary)
        {
            this.WorkingHours = workingHours;
            this.SchoolHours = schoolHours;
        }

        public void Learn()
        {
            Console.WriteLine("I'm learn for {0} hours!", SchoolHours);
        }

        public override void Work()
        {
            Console.WriteLine("I'm working for {0} hours", WorkingHours);
        }
    }
}
```
