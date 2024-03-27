# IEnumerable Excise

```csharp
using System;
using System.Collections.Generic;
using System.Collections;

namespace Coding.Exercise
{
    // TODO
    class Contact
    {
        public string Name { get;set; }
        public string PhoneNumber { get; set; }

        public Contact(string name, string phoneNumber)
        {
            this.Name = name;
            this.PhoneNumber = phoneNumber;
        }

        public void Call(){
            Console.WriteLine($"Calling to {Name}. Phone number is {PhoneNumber}");
        }
    }

    class PhoneBook: IEnumerable<Contact>{

        public List<Contact> Contacts;

        public PhoneBook(){
            Contacts = new List<Contact>{
                new Contact("Andre", "435797087"),
                new Contact("Lisa", "435677087"),
                new Contact("Dine", "3457697087"),
                new Contact("Sofi", "4367697087")
            };
        }
        // solution


        IEnumerator<Contact> IEnumerable<Contact>.GetEnumerator(){
            return Contacts.GetEnumerator();
        }

        IEnumerator IEnumerable.GetEnumerator(){
            throw new NotImplementedException();
        }
        // solution
    }


    public static class Program{
        static public void Main(string[] args){
            PhoneBook MyPhoneBook = new PhoneBook();

            foreach (Contact contact in MyPhoneBook){
                contact.Call();
            }
        }
    }
}
```
