## Applies to [All languages]

# Wrapper structure
All wrappers should follow a similar structure to maintain simplicity and readability for all devevelopers working on this project *and* all developers using our wrappers.

**Backend** - How the wrapper works behind the scenes. <br>
**Frontend** - How the end user interacts with our wrapper.

## Frontend
A few general rules for frontend:
 - All classes/structs/objects used in the front end **should** be prefixed with "Hypixel" e.g. `HypixelPlayer` `HypixelGuild` `HypixelSkyblockProfile` (there may be exceptions, these will be documented per language)
 - Between languages, all class/struct/object names **should** be the same. If you are unsure about what names to use, look at the source code of other wrappers.</br></br>
 - Between languages, all methods of corresponding classes/structs/objects **should** have the same name. These methods **must** return the same data.
 - Methods **must** always be provided with documentation describing what the method returns.

### Need help?
If you have any suggestions, or are unsure of any information, please join our Discord server and ask: [Invite Link](https://discord.com/invite/NkRQHemWtJ)<br>
Thanks so much for contributing to this project ❤️
