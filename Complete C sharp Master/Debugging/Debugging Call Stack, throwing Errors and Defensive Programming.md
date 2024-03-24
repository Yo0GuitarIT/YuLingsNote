# Debugging Call Stack, throwing Errors and Defensive Programming

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

            // var friends = new List<string>();
            var partyFriends = GetPartyFriends(friends, 3);

            foreach (var name in partyFriends)
            {
                Console.WriteLine(name);
            }
        }

        public static List<string> GetPartyFriends(List<string> list, int count)
        {
            // if (list == null)
            // {
            //     throw new ArgumentNullException("List", "List is empty");
            // }

            // if (count > list.Count || count <= 0)
            // {
            //     throw new ArgumentOutOfRangeException(
            //         "count",
            //         "Count can not be greater then elements in the list or lower zero"
            //     );
            // }
            var buffer = new List<string>(list);
            var partyFriends = new List<string>();

            while (partyFriends.Count < count)
            {
                var currentFriend = GetPartyFriend(buffer);
                partyFriends.Add(currentFriend);
                buffer.Remove(currentFriend);
            }

            return partyFriends;
        }

        /// <summary>
        /// This is the logic to fogure out who is a party
        /// </summary>
        /// <param name = "list"></parm>
        /// <returns></returns>

        public static string GetPartyFriend(List<string> list)
        {
            string shortestName = list[0];
            for (var i = 0; i < list.Count; i++)
            {
                if (list[i].Length < shortestName.Length)
                {
                    shortestName = list[i];
                }
            }

            return shortestName;
        }
    }
}

```
