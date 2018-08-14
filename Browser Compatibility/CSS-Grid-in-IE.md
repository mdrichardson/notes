# Getting CSS Grid to Work in IE

*Note: The following list will use `*` or `*s` in place of row/column/rows/columns*

* Always define `grid-*-start` with `-ms-grid-*` or elements will overlap
  * IE defaults `grid-*-start` to `1` if you don't define it yourself
* If you want things to center and it isn't working, it's probably because you defined your grid with rows and not columns, or vice versa.
  * Define both with `-ms-grid-*s: 1fr`, then use `-ms-grid-column-align: center` and `-ms-grid-row-align: center`
* Use `1fr` instead of `auto`, unless you want auto-shrink. This helps with centering.
* Don't use `repeat()`; it doesn't work
* Grid in IE doesn't work with many HTML tags, especially custom ones. Wrap them in `div`s instead of using `<app-component>`