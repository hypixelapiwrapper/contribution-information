## Applies to [Java]

## Overview of Java naming conventions
Variables and methods - Lower Camel Case - `players()` or `getPlayer()` for example

Classes, interfaces, annotations, enums, records - Upper Camel Case - `HypixelPlayer` or `PlayerUtility` for example

Packages - Lower case, separated by dots - Our package name is already configured.

## Commenting
During contribution, you may create hard-to-understand method names.
In this case, please comment it!

Use `@param ......` to explain any non-explainable parameters passed to the method.<br/>
Use `@return ......` to explain any non-explainable return values.

```java
/*
 *  @return An integer representing the amount of exp you are over your previous, full level.
*/
public int getExpToHypixelLevel(long current) {
    return this.whatever;
}
```

Comments should always appear above the method.
