# Stacks

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

# Queues

---

### Feature

- Data can be added from the rear (back) and removed from the front.
- Can’t access the elements in the middle.
- First in first out ( FIFO).

### Queues in Programming

- OS IO request, mouse movements
- Managing web requests in server
- Queuing input in video games

### Queues Operation

- Enqueue (Object obj)：將物件添加到隊列的尾部。這意味著在隊列的尾部添加一個新的項目。
- Object Dequeue()：從隊列的頭部移除並返回項目。這意味著它從隊列的頭部刪除項目並將其返回。
- Object Peek()：返回隊列的頭部項目，但不從隊列中刪除它。這個操作允許你查看隊列的頭部項目而不對隊列進行修改。

**EX.1**

```csharp
namespace QueueDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // define a queue of integers
            Queue<int> queue = new Queue<int>();

            // print the element at the front of the queue
            queue.Enqueue(1);
            Console.WriteLine("The value at the front of the queue is  : {0}", queue.Peek());
            queue.Enqueue(2);
            Console.WriteLine("The value in the queue is  : {0}", queue.Peek()); 
            queue.Enqueue(3);
            Console.WriteLine("The value in the queue is  : {0}", queue.Peek());

            while (queue.Count > 0)
            {
                // Dequeue() will return the element that was remove from the queue
                Console.WriteLine(
                    "The front value {0} was removed from the queue",
                    queue.Dequeue()
                );
                // print the queue count
                Console.WriteLine("Current queue count is : {0} ", queue.Count);
            }
        }
    }
}

// The value at the front of the queue is  : 1
// The value in the queue is  : 1
// The value in the queue is  : 1
// The front value 1 was removed from the queue
// Current queue count is : 2 
// The front value 2 was removed from the queue
// Current queue count is : 1 
// The front value 3 was removed from the queue
// Current queue count is : 0 
```

**EX.2**

```csharp
namespace QueueDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Queue<Order> ordersQueue = new Queue<Order>();
            foreach (Order o in ReceiveOrdersFromBranch1())
            {
                // add each order to the queue
                ordersQueue.Enqueue(o);
            }
            foreach (Order o in ReceiveOrdersFromBranch2())
            {
                // add each order to the queue
                ordersQueue.Enqueue(o);
            }

            // as long as the queue is not empty
            while (ordersQueue.Count > 0)
            {
                // remove the Order at the front of the queue
                // and store it in a variable called currentOrder
                Order currentOrder = ordersQueue.Dequeue();
                currentOrder.ProcessOrder();
            }
        }

        // this method will creat an array of orders and return it
        static Order[] ReceiveOrdersFromBranch1()
        {
            // creat new orders array
            Order[] orders = new Order[]
            {
                new Order(1, 5),
                new Order(2, 4),
                new Order(6, 10)
            };
            return orders;
        }

        static Order[] ReceiveOrdersFromBranch2()
        {
            // creat new orders array and initializing it with some objects of type Order
            Order[] orders = new Order[]
            {
                new Order(3, 5),
                new Order(4, 4),
                new Order(5, 10),
            };
            return orders;
        }
    }

    // a class named order will use it to store instances of it inside a queue
    class Order
    {
        // order ID
        public int OrderId { get; set; }

        // quantity of the order
        public int OrderQuantity { set; get; }

        // simple constructor
        public Order(int id, int orderQuantity)
        {
            this.OrderId = id;
            this.OrderQuantity = orderQuantity;
        }

        //print message on the screen
        public void ProcessOrder()
        {
            // print the message
            Console.WriteLine($"Order {OrderId} processed! ");
        }
    }
}
```
