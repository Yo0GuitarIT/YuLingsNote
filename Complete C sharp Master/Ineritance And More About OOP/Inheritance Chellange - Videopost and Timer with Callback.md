# VideoPost and Timer with Callback

> _延伸上個程式碼內容，新增 VideoPost 的類別。_

### 程式碼

- Program.cs

```csharp
namespace InheritanceVideoPost
{
    class Program
    {
        static void Main(string[] args)
        {
            Post post1 = new Post("Thanks for the birthday wishes", true, "Denis Paajuta");
            Console.WriteLine(post1.ToString());

            VideoPost videoPost1 = new VideoPost(
                "Failed Video",
                "Alen Chen",
                "http;//video.com/failvideo",
                10,
                true
            );
            Console.WriteLine(videoPost1.ToString());

            ImagePost imagePost1 = new ImagePost(
                "Check out my new shoes",
                "Denis Panjuta",
                "https://images.com/shoes",
                true
            );
            Console.WriteLine(imagePost1.ToString());

            videoPost1.Play();
            Console.WriteLine("Press ant key to stop the video");
            Console.ReadKey();
            videoPost1.Stop();
        }
    }
}

```

- VideoPost.cs

```csharp
using System.Diagnostics;
using System.Linq.Expressions;

namespace InheritanceVideoPost
{
    class VideoPost : Post
    {
        // member fields
        protected bool isPlaying = false;
        protected int currDuration = 0;
        Timer timer;

        // Properties
        protected string VideoURL { get; set; }
        protected int Length { get; set; }

        public VideoPost() { }

        public VideoPost(
            string title,
            string sendByUsername,
            string videoURL,
            int length,
            bool isPublic
        )
        {
            // The following properties and the GetNextID method are inherited from Post.
            this.ID = GetNextID();
            this.Title = title;
            this.SendByUsername = sendByUsername;
            this.IsPublic = isPublic;

            // Property VideoURL is a member of VideoPost,  but not of Post
            this.VideoURL = videoURL;
            this.Length = length;
        }

        public void Play()
        {
            if (!isPlaying)
            {
                isPlaying = true;
                Console.WriteLine("Playing");
                timer = new Timer(TimerCallback, null, 0, 1000);
            }
        }

        public void Stop()
        {
            if (isPlaying)
            {
                isPlaying = false;
                Console.WriteLine("Stop at {0}s", currDuration);
                currDuration = 0;
                timer.Dispose();
            }
        }

        private void TimerCallback(Object o)
        {
            if (currDuration < Length)
            {
                currDuration++;
                Console.WriteLine("Video at {0}s", currDuration);
                GC.Collect();
            }
            else
            {
                Stop();
            }
        }

        public override string ToString()
        {
            return String.Format(
                "{0} - {1} - {2} - {3} by {4}",
                this.ID,
                this.Title,
                this.VideoURL,
                this.Length,
                this.SendByUsername
            );
        }
    }
}

```

### 範例說明

這段程式碼是一個名為 `VideoPost` 的類別，它衍生自 `Post` 類別。讓我們來解釋一下這段程式碼中的一些關鍵部分：

1. `timer = new Timer(TimerCallback, null, 0, 1000);`：

   - 這行程式碼建立了一個新的 `Timer` 物件，它會以一定的間隔（此處為 1000 毫秒，即每秒）調用一個指定的回調函式 `TimerCallback`。
   - 第一個參數 `TimerCallback` 是要執行的方法。
   - 第二個參數 `null` 是傳遞給回調方法的狀態物件，這裡我們沒有使用，所以設為 `null`。
   - 第三個參數 `0` 表示延遲多少毫秒後開始第一次執行回調方法，這裡設為 0 表示立即開始。
   - 第四個參數 `1000` 表示每次調用回調方法之間的間隔時間。

2. `timer.Dispose();`：

   - 這行程式碼是釋放 `Timer` 物件的資源，用於停止計時器。
   - 這樣做是為了確保在不需要計時器時釋放相關的資源，防止資源洩漏和效能問題。

3. `private void TimerCallback(Object o)`：

   - 這是一個私有方法，用於作為計時器的回調方法。
   - 每當計時器觸發時，就會執行這個方法。
   - 在這個方法中，它檢查了當前的播放時間是否小於視頻的長度，如果是則增加當前播放時間，並輸出當前播放的時間。
   - 如果播放時間等於或超過視頻的長度，則調用 `Stop()` 方法停止播放。

4. `GC.Collect()` 是在 C# 中用來強制執行垃圾回收的方法。它可以在特定情況下幫助改善程式的性能和内存使用情況。

   - **垃圾回收 (Garbage Collection)**：在 .NET 環境中，垃圾回收是一個自動管理記憶體的機制。當對象不再被引用時，它們佔用的記憶體會被自動回收，以便重新利用。這樣可以避免內存泄漏和提高程式效能。

   - **`GC.Collect()` 方法**：`GC.Collect()` 方法是用來觸發垃圾回收的。當呼叫這個方法時，系統會立即進行一次垃圾回收，並嘗試釋放沒有被引用的對象佔用的記憶體。

   - **使用時機**：通常情況下，不需要手動呼叫 `GC.Collect()` 方法，因為.NET 框架會自動管理記憶體並在需要時執行垃圾回收。然而，有時候在某些情況下，特別是在開發高性能應用時，可能需要手動觸發垃圾回收以釋放大量未使用的記憶體，從而減少系統的內存壓力。
