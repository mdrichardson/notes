# Named vs. Default Imports

If you export a JS class with:

`export default 'ABC'`

it can be named anything when imported, with:

`import XYZ from './ABC'`
or
`import ABC from './ABC'`

However, if you export with:

`export const ABC = 'ABC'`

it must be imported with:

`import { ABC } from './ABC'`

If you actually *want* to name it (not recommended):

`import { ABC as XYZ } from './ABC'`

A module can only have one default export, but as many named exports as you'd like.

The default exports tend to be used for whatever you normally expect to get from the module. The named exports tend to be used for utilities that might be handy, but aren’t always necessary. 