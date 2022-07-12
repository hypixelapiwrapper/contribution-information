## Applies to [All languages]

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
    - A method that returns the friends of the player in the form of a list of **`HypixelPlayer`** data structures.
    - A method that returns the online status of the player in the form of a **`HypixelPlayerStatus`** data structure.
    - A method that returns the recent games of the player in the form of a list of **`HypixelGameSession`** data structures.
    - A method that returns either a **`HypixelGuild`** if the player is in a guild or nothing if the player is not in a guild.
</br></br>
 - **`HypixelGuild` must** implement the following methods:
    - ...

Need help?
--
If you have any suggestions, or are unsure of any information, please join our Discord server and ask: [Invite Link](https://discord.com/invite/NkRQHemWtJ)<br>
Thanks so much for contributing to this project ❤️
