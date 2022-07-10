## Applies to [Java, Python, JavaScript]

# Wrapper structure
All wrappers should follow a similar structure to preserve ease for the end user (the developer using our wrapper).

**Backend** - How the wrapper works behind the scenes. <br>
**Frontend** - How the end user interacts with our wrapper.

## Backend
The main features of our wrapper are:
 - Dynamic loading of data, based on end users needs (explained below).
 - Asynchronous design.
 - Automatic key ratelimiting.
 - Follow's a similar design matter to other wrappers.
 - Also supports a handful of other APIs, including Mojang and possibly observer.

### Dynamic loading of data - Explanation
_Take this example:_
Our `HypixelPlayer` class can request data from multiple endpoints (`/player`, `/recentgames`, `/friends`).
Now by default, the `HypixelPlayer` object just stores a `UUID` and/or `username` field, and contains no data from the Hypixel API.

```java
HypixelPlayer player = api.players().named("Mqlvin"); // this got no player data, it just created a shell for a player.

int nwLevel = player.getNetworkLevel(); // this requested data
```

Once you run the `getNetworkLevel()` method, the `player` object realises it hadn't already requested any data from the `/player` endpoint.
The `player` object does request data, and it returns the network level.

Now, you call for more data from that `/player` endpoint.

```java
HypixelRank rank = player.getRank(); // this did not request any more data

List<HypixelFriend> friends = player.getFriends(); // this did request more data, this time from the '/friend' endpoint
```

Because the `player` object has already requested data from the `/player` endpoint, it already has the rank data stored locally, it returns the rank data.

Now, why do we use this system? Two reasons:
1. It allows classes to be feature rich, allowing methods for a lot more information than a default wrapper (as we can fit multiple endpoints with related data into one class).
2. It cuts down on requests tremendously. If you created a player object, just to get their friends, a normal wrapper would've uselessly sent a request to get player data, when it was unneeded, before sending a request to get friends.

### Need help?
If you have any suggestions, or are unsure of any information, please join our Discord server and ask: [Invite Link](https://discord.com/invite/NkRQHemWtJ)<br>
Thanks so much for contributing to this project ❤️
