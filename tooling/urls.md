
# URL resolution and aliases

Webpack will resolve URLs for you. You can use relative URLs in any context (importing, HTML assets, CSS etc.) to point to a specific file from the specific file you are writing the URL in.

We can also use aliases though, so that you don't always have to keep track of the relative positioning of specific source files (which easily leads to bugs when refactoring).

Aliases are configured in [`src/config/tooling/aliases.js`](https://github.com/Eiskis/bellevue/tree/master/src/config/tooling/aliases.js).

## Using aliases

JavaScript (**no** `~` prefix):

```js
import metaConfig from '@config/meta';
const imgPath = require('@assets/logo.png');
```

HTML (**with** `~` prefix):

```html
<img src="~@assets/logo.png">
```

Sass (**with** `~` prefix):

```scss
@import '~@styles-global';

.foo {
	background-image: url('~@assets/logo.png');
}
```

Aliases work in `.vue` files as well as standalone JS/Sass/HTML files.
