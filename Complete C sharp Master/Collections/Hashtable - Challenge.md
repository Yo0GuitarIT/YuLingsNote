# Hashtable - Challenge

---

```csharp
using System.Collections;

namespace HashTableChallenge
{
    class Program
    {
        static void Main(string[] args)
        {
            Hashtable studentsTable = new Hashtable();
            Student[] students = new Student[5];
            students[0] = new Student(1, "Denis", 88);
            students[1] = new Student(2, "Olaf", 97);
            students[2] = new Student(6, "Ragner", 65);
            students[3] = new Student(1, "Luise", 73);
            students[4] = new Student(4, "Levi", 58);

            foreach (Student people in students)
            {
                if (!studentsTable.ContainsKey(people.Id))
                {
                    studentsTable.Add(people.Id, people);
                    Console.WriteLine("Student with ID : {0} was add!.", people.Id);
                }
                else
                {
                    Console.WriteLine(
                        "Sorry, A student with the same ID already exist:{0}",
                        people.Id
                    );
                }
            }
        }
    }

    class Student
    {
        // property called  Id
        public int Id { get; set; }

        //property called name
        public string Name { get; set; }

        //property called GPA
        public float GPA { get; set; }

        //simple construstor
        public Student(int id, string name, float gpa)
        {
            this.Id = id;
            this.Name = name;
            this.GPA = gpa;
        }
    }
}

```