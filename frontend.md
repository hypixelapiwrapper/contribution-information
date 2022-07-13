### Applies to [All languages]

# Frontend
A few general rules for frontend:
--

 - Languages **should** follow their most used naming conventions separately.</br></br>
 - All classes/structs/objects used in the front end **should** be prefixed with "Hypixel" e.g. `HypixelPlayer` `HypixelGuild` `HypixelSkyblockProfile` (there may be exceptions, these will be documented per language)
 - Between languages, all classes/structs/objects **should** have similar names. If you are unsure about what names to use, look at the source code of other wrappers.</br></br>
 - Between languages, all methods of corresponding classes/structs/objects **should** have similar names. These methods **must** return the same data.
 - Methods **must** always be provided with documentation describing what the method returns.

Detailed information for frontend:
--
**Note**: When reading the information below, multiple methods that return the same data **must** only ever be allowed because of multiple independent arguments.
**Note**: This information explicitly does not describe how the different data structures should behave internally or what data they need to store. This is reserved for the backend and should not concern the frontend enough to list here.

- A main data structure called `HypixelAPI` **must** exist in the wrapper. `HypixelAPI` **must** store the following data:

| name | type | note |
| --- | --- | --- |
| API Key | **`UUID`** | This is a key retrieved from Hypixel and provided by the developer. |
| Cache | **`HypixelCache`** | This may be a reference. `HypixelCache` is an interface, see below. |
| Cache Strategy | **`HypixelCacheStrategy`** | This may be a reference. `HypixelCacheStrategy` is an interface, see below. |

- **`HypixelAPI` must** implement one or more methods for every row in the following table:

| arguments | return type | note |
| --- | --- | --- |
| or `UUID` of the player</br>or `Name` of the player | **`HypixelPlayer`** | `Name` is a string. |
| or `UUID` of player in guild</br>or `ID` of requested guild</br>or `Name` of the requested guild | **`HypixelGuild`** | `Name` is a string. |
| | **`HypixelLeaderboards`** |
| | **`HypixelPunishmentStats`** |

**Note**: If a language's design and conventions permit it, these methods may be structurally grouped together, branching off of `HypixelAPI`.

- **`HypixelPlayer`** **must** implement the following methods:

| arguments | return type | note |
| --- | --- | --- |
| | **`HypixelPlayerStatus`** | This returns the online status of the player. |
| | collection of **`HypixelFriendShip`** | This returns the friends of the player. |
| | collection of **`HypixelGameSession`** | This returns the recent games of the player. |
| | optional **`HypixelGuild`** | This returns guild of the player. |

- **`HypixelPlayerStatus`** **must** implement the following methods:

| arguments | return type | note |
| --- | --- | --- |
| | **`boolean`** | This returns whether the player is currently online. |
| | **`GameType`** | This returns the game the player is in. |
| | **`String`** | This returns the mode of the game. |
| | **`String`** | This returns the map of the game. |

- **`HypixelFriendShip`** **must** implement the following methods:

| arguments | return type | note |
| --- | --- | --- |
| | **`HypixelPlayer`** | This returns the player who sent the friend request. |
| | **`HypixelPlayer`** | This returns the player who accepted the friend request. |
| | **`Timestamp`** | This returns the date and time at which the friendship started. |

- **`HypixelGameSession`** **must** implement the following methods:

| arguments | return type | note |
| --- | --- | --- |
| | **`Timestamp`** | This returns the date and time at which the game started. |
| | **`Timestmap`** | This returns the date and time at which the game ended. |
| | **`GameType`** | This returns the specific game the player was in. |
| | **`String`** | This returns the mode of the game. |
| | **`String`** | This returns the map of the game. |

 - **`HypixelGuild` must** implement the following methods:
    - ...

Need help?
--
If you have any suggestions, or are unsure of any information, please join our Discord server and ask: [Invite Link](https://discord.com/invite/NkRQHemWtJ)<br>
Thanks so much for contributing to this project ❤️
