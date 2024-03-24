# Member And Finalizers / Destructors

---

```csharp
// Programe.cs

namespace membersC
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Members member1 = new Members();
            member1.Introducing(true);
        }
    }
}

```

```csharp
// Members.cs

using System.Diagnostics;
using System.Runtime.CompilerServices;

namespace membersC
{
    class Members
    {
        // member - private field
        private string memberName;
        private string jobTitle;
        private int salary;

        // member - public field
        public int age;

        //  member - property - exopose jobTitle safely - properties start with a capital letter
        public string JobTitle
        {
            get { return jobTitle; }
            set { jobTitle = value; }
        }

        //public member Method - can be  called from other class
        public void Introducing(bool isFriend)
        {
            if (isFriend)
            {
                SharingPrivateInfo();
            }
            else
            {
                Console.WriteLine(
                    "Hi, my name is {0}, and my job title is {1}. I'm {2} years old",
                    memberName,
                    jobTitle,
                    age
                );
            }
        }

        private void SharingPrivateInfo()
        {
            Console.WriteLine("My Salary is {0}", salary);
        }

        //member constructor
        public Members()
        {
            age = 30;
            memberName = "Lucy";
            salary = 60000;
            jobTitle = "Developer";
            Console.WriteLine("Object Created");
        }

        // member - finalizer - destructor
        ~Members()
        {
            // cleanup statements
            Console.WriteLine("Deconstruction of Members object");
            Debug.Write("Deconstruction of Members object");
        }
    }
}

```