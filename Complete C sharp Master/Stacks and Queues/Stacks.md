# Stacks and Queues

## Stacks

---

### Feature

- Data can be added / remove from top.
- Can’t access the elements in the middle.
- First come last out or last in, first out (LIFO).

### Stacks in Programming

- Reversing Data
- Web browser back button
- Undo/Redo buttons

### Stack Operations

- Push (Object obj) : 將物件推入堆疊的頂部。這意味著在堆疊中添加新的項目，將其放置在現有項目的上方。
- Object Pop() : 從堆疊的頂部移除並返回項目。這意味著它從堆疊中刪除頂部的項目並將其返回。
- Object Peek() : 返回堆疊的頂部項目，但不從堆疊中刪除它。這個操作允許你查看堆疊的頂部項目而不對堆疊進行修改。

```csharp
namespace StackDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // define a new stack
            Stack<int> stack = new Stack<int>();
            // The Stack could alternative hold any other type of Object (strings, your own Classes etc.)
            // But only one type per stack! (bc.generic)

            // add elements to the stack using Push()
            // Peek() will return the element at the top of the stack without removing it
            stack.Push(1);
            Console.WriteLine("Top value in the stack is {0}", stack.Peek());
            stack.Push(2);
            Console.WriteLine("Top value in the stack is {0}", stack.Peek());
            stack.Push(3);
            // remove items from stack
            int myStackItem = stack.Pop();
            Console.WriteLine("Pop item {0}", myStackItem);
            Console.WriteLine("Top value in the stack is {0}", stack.Peek());

            // as long as the count is > 0, as long as the stack is not empty
            while (stack.Count > 0)
            {
                // Pop()wil return the element that was remove from the stack
                Console.WriteLine("The Top value {0} was remove from the stack", stack.Pop());
                // print the stack out
                Console.WriteLine("Curret stack count is : {0}", stack.Count);
            }

            int[] numbers = new int[] { 8, 2, 3, 4, 7, 6, 2 };
            // define a new stack of int
            Stack<int> myStack = new Stack<int>();
            foreach (int number in numbers)
            {
                // print it
                Console.Write(number + " ");
                // push it into our stack(add)
                myStack.Push(number);
            }

            Console.WriteLine("");
            Console.WriteLine("the numbers in reverse :");
            // as long as our stack in not empty
            while (myStack.Count > 0)
            {
                // Pop it and store in a variable
                int number = myStack.Pop();
                // Print the value we poped
                Console.Write(number + " ");
            }

        }
    }
}
```
