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
**Note**: While reading the information below, every *method* that takes multiple arguments should be implemented as either multiple methods with different parameter types or multiple methods denoting the difference in argument type in the name.

 - A main data structure called `HypixelAPI` **must** exist in the wrapper. `HypixelAPI` **must** store the following data:
    - An **`API key`**: This is a key retrieved from Hypixel and provided by the developer, this should be in the form of a **UUID**.
    - A (reference to a) **`HypixelCache`**: This is a data structure that implements the `HypixelCache` interface, see below.
    - A (reference to a) **`HypixelCacheStrategy`**: This is a data structure that implements the `HypixelCacheStrategy` interface, see below.
</br></br>
 - **`HypixelAPI`** **must** implement the following methods (for the different data structures, see below):
    - A method that returns a **`HypixelPlayer`** data structure. This method takes either a UUID or the name of the requested player as argument.
    - A method that returns a **`HypixelGuild`** data structure. This method takes either the UUID of a player in the requested guild, the id of the requested guild or the name of the requested guild as argument.
    - A method that returns a **`HypixelLeaderboards`** data structure. This method takes no arguments.
    - A method that returns a **`HypixelPunishmentStats`** data structure. This method takes no arguments.
    - **Note**: If a language's design and conventions permit it, these methods may be structurally grouped together, branching off of `HypixelAPI`.
</br></br>
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
