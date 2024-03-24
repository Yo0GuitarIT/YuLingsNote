# Debugging Basic

_VSCode 的偵錯工具是一個非常實用的工具，可以幫助您找到並修復程式碼中的錯誤。您可以使用上述功能來觀察程式碼的執行狀況，了解程式的執行流程，並找到錯誤的原因。_

### 如何使用 VSCode 偵錯工具


> 1. 在 VSCode 中開啟專案。
> 2. 按下 F5 或點選`偵錯`功能表的`開始偵錯`命令。
> 3. VSCode 會啟動偵錯器並執行程式碼。

在偵錯過程中，使用以下功能來觀察程式碼的執行狀況：

- **Breakpoint**:中斷點是讓程式在特定位置暫停執行的指令。設定多個中斷點，以便在程式碼的不同位置進行檢查。
- **Continue**:Continue 命令會讓程式繼續執行，直到遇到下一個中斷點或執行結束。
- **Step over**:讓程式逐行執行，但會跳過函式的呼叫。
- **Step into**:讓程式逐行執行，並進入函式的呼叫。
- **Step out**:跳出目前所在的函式，並回到呼叫該函式的程式碼。
- **Restart**:重新啟動偵錯器並重新執行程式碼。
- **Stop**:停止偵錯器並結束程式碼的執行。

```csharp
namespace Debugging
{
    class Program
    {
        static void Main(string[] args)
        {
            var friends = new List<string>
            {
                "Friank",
                "Joe",
                "Michelle",
                "Andy",
                "Maria",
                "Carlos",
                "Angelina"
            };
            var partyFriends = GetPartyFriends(friends, 4);

            foreach (var name in partyFriends)
            {
                Console.WriteLine(name);
            }
        }

        public static List<string> GetPartyFriends(List<string> list, int count)
        {
            var partyFriends = new List<string>();

            while (partyFriends.Count < count)
            {
                var currentFriend = GetPartyFriend(list);
                partyFriends.Add(currentFriend);
                list.Remove(currentFriend);
            }

            return partyFriends;
        }

        public static string GetPartyFriend(List<string> list)
        {
            string shortestName = list[0];
            for (var i = 0; i < list.Count; i++)
            {
                if (list[i].Length > shortestName.Length)
                {
                    shortestName = list[i];
                }
            }

            return shortestName;
        }
    }
}

```
