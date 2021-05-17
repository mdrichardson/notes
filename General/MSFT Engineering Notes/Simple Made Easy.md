# Summary

Rich Hickey emphasizes simplicity’s virtues over easiness’, showing that while many choose easiness they may end up with complexity, and the better way is to choose easiness along the simplicity path.

## Link

https://www.infoq.com/presentations/Simple-Made-Easy/

# Notes

* When we talk about simplicity and "only does one thing", we really mean there's no interleaving between multiple things instead of "only one thing can be done, period"
* "Simple" vs. "Easy": Easy is relative
* We focus too much on the developer experience/convenience and not enough on software quality/correctness and ease of maintenance
* Every software bug:
  * has passed a type checker
  * has passed all of your tests
* Ignoring complexity will slow you down over the long haul
  * Sprinters can run at full speed for only very short distances. That's why we start a new "sprint" every month (joke)
* Benefits of Simplicity
  * Ease of understanding
  * Ease of change
  * Easier debugging
  * Flexibility
    * policy
    * location etc
* State always makes things complex. Avoid when possible.
* Programming isn't about typing. It's about thinking.
* Abstract things away, when possible, and connect together through polymorphism
* Have small interfaces and many subcomponents