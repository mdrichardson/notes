# Writing Clean Code

## General

1. Use meaningful variable and function names
    * Better to be meaningful than short
2. Code should speak for itself whenever possible
    * Code should be written so that intention is clear
    * Better to be readable than fancy
    * Use comments only when code cannot speak for itself
3. Leave code better than you found it
    * When you're reviewing, improve the code as possible
4. Functions and methods should do one thing and do it well
    * If you're passing many arguments, it's a good indicator that your function does too much and should be broken up
5. Write tests. Use the tests to improve code

## Notes on [Clean Code by Robert Martin](https://smile.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM?sa-no-redirect=1)

### Meaningful Names

* Use Intention-Revealing Names
  * Not `d` but `elapsedTimeInDays`
* Avoid Disinformation
  * Use `accounts` instead of `accountList` in case variable isn't a `list`
* Make Meaningful Distinctions
  * Instead of:
    ```js
    someList[2] = someList[1]
    ```
  * Use:
    ```js
    let source = 1;
    let destination = 2;
    someList[destination] = someList[source]
    ```
* Avoid "Noise Words" like `Info` in `productInfo`
* Use pronounceable and searchable names
  * Not `ymdoe` but `yearMonthDayOfEvent`
  * Single letter names, like `a` or `i` are difficult to search for. Use the full word like `apples` or `index` unless in extremely limited scope, like a loop
* Avoid Mental Maps
  * Instead of `this` or `that`, be specific about what `this` and `that` represents so readers don't have to think about it
* Class names should have nouns like `processor` or `manager`. Method names should have verbs like `get` and `set`
* Use appropriate words
  * No slang, cute, or inside joke words
  * Avoid 'puns' that might mean different things in different uses, like `add` for appending something to an object `add` for math
  * Use solution names like `factory` and `decorator`
* Add to the name with meaningful context
  * Instead of `firstName` and `lastName`, you might use `addressFirstName` and `addressLastName`
    * Better to just use an `Address` class