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

#### Key Points

* Make them very descriptive and easy to understand exactly what they're for

#### General

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

### Functions

#### Key Points

* Keep them small -- under 20 lines
* Functions should be transparently obvious
* Each function tells a story
* Each function leads you to the next in a compelling order

* How-To:
  * Write ugly, long functions with a long list of arguments
  * Write unit tests that cover all of the functions
  * Massage and refine the code. Break everything out into classes to keep the tests passing

#### General

* The blocks within `if`, `while`, and `else` statements should be one line long and should be a function call
  * The function call should have a nice, descriptive name
* Functions should not indent more than one or two levels
* **Functions should do one thing. They should do it well. They should do it only.**
  * If a function is divided into sections, it's probably doing too many things
  * Avoid switch statements except to create polymorphic objects. They do more than one thing.
* Write functions top to bottom
  * Each functions should provide further instructions on the one before it
* Use descriptive names
  * A long, descriptive name is better than a short, enigmatic one
    * It's also better than a long comment explaining the function
  * Be consistent with your names and try to use the same verbs, nouns, etc.
    * *includeSetupAndTeardownPages, includeSetupPages, includeSetupPage...*
* Use as few arguments as possible
  * Avoid output arguments
  * When a funciton must have multiple arguments, it's better to wrap them in an argument
    * Instead of `makeCircle(double x, double y, double radius)`, use `makeCircle(Point center, double radius)`
* Encode the name of the arguments into the function
  * Instead of `assertEquals(expected, actual)`, use `assertExpectedEqualsActual(expected, actual)`
    * The function name tells you more about the arguments, particularly the order they are supposed to go in
* Functions should have no side-effects
  * They should behave exactly like their name describes
    * If you have a function `checkPassword()`, it should only check a user's password, and not proceed to also log them in
* Command/Query Separation
  * Functions should either *do* something or *answer* something, but not both
* Prefer using *Exceptions* over error codes
  * Error codes are usually wrapped in other classes and then the code becomes dependent on them.
    * There's a tendency to not update these enough and to re-use them when they shouldn't be. Better to just use *Exceptions*
* Methods with *try/catch* should only have this structure and nothing else
* Don't repeat yourself

### Code Comments

#### Key Points

* If we were expressive enough in our programming language, we shouldn't need comments
* The more comments we have to use, the worse our code is
* Code changes and evolves but comments don't always get updated
  * This leads to comments being innacurate and misleading

#### General

* Comments don't make up for bad code
  * If you're about to write a comment, see if you can clean up the code to make it more easily understandable and the comment unnecessary
* Good comments  
  * The only good comment is the comment you found a way not to write
  * Legal comments - put all terms and conditions in an external document
  * Informative - provide information related to how to implement and how a decision was made
  * Warn of consequences - Warn other programmers about changing the function or that it takes a long time to run, etc
  * TODO - these are find, but make sure they are removed regularly
  * Amplification - If something is extremely important, you can use comments to amplify its importance
* Bad comments
  * Redundant - reading the code should be enough. The comment should not take longer to read than the code or be less clear
  * Journal - We have git logs and source control. No need to note the steps taken with comments
  * Position markers - No need for banners like `// Actions //////////////////`. They're just noise,
    * Separate it out into a different file, instead
  * Commented-out code - Just delete it. We have source control

### Formatting

#### Key Points

* Make it look professional
* Be consistent
* In a team, everybody should comply to the same rules

#### General

* Vertical formatting
  * Small files are easier to understand than large ones.
  * Keep each file under 500 lines
* Vertical Density
  * Useless comments between every line make it difficult to read. Just avoid comments
* Vertical Distance
  * Variables should be declares as close to their usage as possible
    * Since our functions are short, put all variable declarations at the top when possible
  * If one function calls another, they should be vertically close
  * The caller function should be above the callee
  * Conceptual affinity - Functions that perform similar tasks should be vertically grouped together
* Vertical Ordering
  * Downward direction - Concepts should flow like a newspaper: high level at the top, then low level details as you get further down
* Horizontal Formatting
  * No wider than 120 characters
  * Don't use horizontal alignment. Just use `var a = 10` instead of `var a =       10` and trying to line up values with other variables
