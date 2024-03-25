# Inheritance Demo

## example
- Program.cs
```csharp
namespace InheritanceC
{
    class Program
    {
        static void Main(string[] args)
        {
            Post post1 = new Post("Thanks for the birthday wishes", true, "Denis Paajuta");

            Console.WriteLine(post1.ToString());

            ImagePost imagePost1 = new ImagePost(
                "Check out my new shoes",
                "Denis Panjuta",
                "https://images.com/shoes",
                true
            );
            Console.WriteLine(imagePost1.ToString());
        }
    }
}

```

- Post.cs
```csharp
namespace InheritanceC
{
    class Post
    {
        private static int currentPostId;

        // properties
        protected int ID { get; set; }
        protected string Title { get; set; }
        protected string SendByUsername { get; set; }
        protected bool IsPublic { get; set; }

        // Default constructor.
        // If a derived class does not invoke a base-class constructor explicitly,
        // the default constructot is called implicitly.

        public Post()
        {
            ID = 0;
            Title = "My First Post";
            IsPublic = true;
            SendByUsername = "Denis Panjuta";
        }

        // Instance constructor that has thress parameters
        public Post(string title, bool isPublic, string sendByUsername)
        {
            this.ID = GetNextID();
            this.Title = title;
            this.IsPublic = isPublic;
            this.SendByUsername = sendByUsername;
        }

        protected int GetNextID()
        {
            return ++currentPostId;
        }

        public void Update(string title, bool isPublic)
        {
            this.Title = title;
            this.IsPublic = isPublic;
        }

        // Virtual method override of the ToString method that is inherited
        // from System.Oject.
        public override string ToString()
        {
            return String.Format("{0} - {1} - by {2}", this.ID, this.Title, this.SendByUsername);
        }
    }
}

```

- ImagePost.cs
```csharp
namespace InheritanceC
{
    // imagePost derives from Post and adds a property (ImageURL) and two constructors
    class ImagePost : Post
    {
        public string ImageURL { get; set; }

        public ImagePost() { }

        public ImagePost(string title, string sendByUsername, string imageURL, bool isPublic)
        {
            // the following propertirs and the GetNextID method are inheritfed from Post.
            this.ID = GetNextID();
            this.Title = title;
            this.SendByUsername = sendByUsername;
            this.IsPublic = isPublic;

            // Property ImageURL is member of ImagePost, but not of Post
            this.ImageURL = imageURL;
        }

        // Virtual method override of the ToString method that is inherited
        // from System.Oject.
        public override string ToString()
        {
            return String.Format(
                "{0} - {1} - {2} - by {3}",
                this.ID,
                this.Title,
                this.ImageURL,
                this.SendByUsername
            );
        }
    }
}

```

## 說明

1. **`Post` 類別**：
   - 定義了一個 `Post` 類別，具有屬性 `ID`、`Title`、`SendByUsername` 和 `IsPublic`。
   - 這個類別有兩個建構函式，其中一個是預設建構函式，另一個是接受三個參數的建構函式，用於初始化屬性。
   - 有一個保護的方法 `GetNextID()`，用於獲取下一個帖子的 ID。
   - 定義了一個 `Update()` 方法，用於更新帖子的標題和是否公開。
   - 重寫了 `ToString()` 方法，用於將帖子的相關資訊轉換為字串表示。

2. **`ImagePost` 類別**：
   - 衍生自 `Post` 類別，並添加了一個名為 `ImageURL` 的屬性。
   - 有兩個建構函式，一個是預設建構函式，另一個是接受四個參數的建構函式，用於初始化屬性。
   - 重寫了 `ToString()` 方法，以包含圖片的 URL。

3. **`Program` 類別**：
   - 在 `Main` 方法中創建了一個 `Post` 和一個 `ImagePost` 的實例，並調用了它們的 `ToString()` 方法。

> 這個範例展示了如何使用繼承來重用代碼並擴展類別的功能。  
> 通過 `ImagePost` 類別繼承自 `Post` 類別，我們可以共享 `Post` 類別的屬性和方法，同時添加了特定於圖像帖子的屬性。
