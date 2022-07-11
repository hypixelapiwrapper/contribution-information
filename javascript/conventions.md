## Applies to [JavaScript]

## Overview of JavaScript naming conventions
Variables and methods should be in **camelCase**.
- For variables or properties, the name would be preferable in the form of `nounNoun` or `adjectiveNoun`, and as brief as possible without being unprecise. For instance, `rewardedCoins` is good but not `coinsRewardedToUser`. Special variables like `i` is ok.
- For methods, prefer `verbNoun` or `verb`. For instance, `getPlayer()` is good, but not `player()`.
- Class names should be in **PascalCase**. For instance, `HypixelPlayer` or `PlayerUtility` is good, but not `skyblockAuctions`
- Please don't touch the package name. Please.

## Commenting & Documenting

As per the **ESLint** rules enforced for this project, you need to properly document, using JSDoc, each method and property of each class. Please use standard American English when commenting, and prefer formal language. <br/>
If you don't know how to use **ESLint**, please see the available examples in other parts of the code.

- Below are some good examples
- All the comments starting in `//` are there to help you understand
```javascript
// This JSDoc is documenting the HypixelAPI class. Because the name is intuitive, there's no need to elaborate too much
/**
 * Hypixel API Class
 */
class HypixelAPI {
  // Similarly, constructor is basic JS, not much docs.
  // To document a parameter
  // @param {type} name-of-argument *comments*
  /**
   * Constructor
   * @param {string} key API Key
   */
  constructor(key) {
    // Document a property of type string.
    /**
     * @type {string}
     */
    this.key = key;
  }
  // string? = string or null
  // @return documents the returned value of getKey()
  /**
   * Gets the key
   * @return {string?}
   */
  getKey() {
    return this.key;
  }
}
```

## Code Formatting

As per the **ESLint** rules enforced for this project, you need to properly format the code per ESLint rules.<br/>
*Feel free to ask for rule changes. Currently we are following the standard ruleset by Google.*
**PLEASE REMEMBER, IF YOUR PR DOESN'T PASS THE ESLINT TEST, IT WON'T BE MERGED**
This is to ensure styling consistency in JS, a language with few styling restrictions that can cause messy code.

Check if your IDE supports ESLint (on VSC, there's a plugin called ESLint), use that to lint if necessary.

```bash
# Installs dependencies
npm i
# Installs ESLint globally
npm i eslint -g
# Checks for errors (make sure you are in root directory)
eslint .
# Checks and fix automatically fixable errors (make sure you are in root directory)
eslint . --fix
```

## Testing

*Feel free to add or change or remove tests in `tests/index.js`*

```bash
npm run test
```

**PLEASE CHECK IF YOUR CODE WORKS, AND WHAT YOU'VE CHANGED/ADDED IS CORRECT & ACCURATE, AS THIS MIGHT NOT BE DETECTABLE WITH TESTS**

## Additional Information

- (Applies to version 1.0 and above) Please make sure to mention in your pull request if it contains breaking changes (i.e renaming a method)