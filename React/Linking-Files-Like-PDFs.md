# Linking to Files like PDFs, Internally

React does this weird thing where clicking the link the first time works, but subsequent links just opens the root web page.

To fix this, import the file as a module:

```jsx
import pdfLink from '../xyz.pdf
...
<a href={ pdfLink }>
```