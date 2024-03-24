## Queues

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
