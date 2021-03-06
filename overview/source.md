
# Source code structure

[Browse source on GitHub](https://github.com/Eiskis/bellevue)

```
e2e/                              // End-to-end tests (on Nightwatch)
	└── myTest.e2e.js

src/
	├── assets/                   // Generic asset files such as images
	├── components/               // Views, single-file .vue components
	├── config/                   // Centralised configuration for tooling and runtime code
	.	├── dev/                  // Config overrides for development mode
	.	├── tooling/              // Configuration that won't be available runtime
	.	.	├── aliases.js
	.	.	├── manifest.js
	.	.	├── robotsTxt.js
	.	.	├── routes.js
	.	.	├── sitemap.js
	.	.	└── svgo.js
	.	├── analytics.js
	.	├── build.js
	.	├── meta.js
	.	├── paths.js
	.	├── router.js
	.	└── styles.js
	.
	├── directives/               // Vue directives
	├── mixins/                   // Vue mixins (NOT Sass mixins)
	├── models/                   // JS business logic objects
	├── plugins/                  // Vue plugins
	├── services/                 // JS custom (reactive) services
	└── styles/                   // Global base styling and style utilities
	.	├── defaults/
	.	├── functions/
	.	├── keyframes/
	.	├── mixins/
	.	├── transitions/
	.	├── utilities/
	.	|
	.	├── constants.scss        // Global Sass variables and defaults
	.	├── font-face.scss        // Generates @font-face rules for local web fonts
	.	├── functions.scss        // All Sass functions
	.	├── mixins.scss           // All Sass mixins
	.	└── normalize.scss        // Global resets
	.
	├── svg/                      // SVG assets to optimize and compile
	├── util/                     // JS custom utilities
	├── vendor/                   // Vendor libraries setup
	.	├── vue-router.js         // Vue plugin setup
	.	└── vue.js                // Main Vue instance setup
	.
	├── index.html.ejs            // Main HTML template
	└── main.js                   // Entry point for client app

static/                           // Static files to host alongside product, including app icons
	├── _redirects
	├── favicon.png
	├── icon-48.png
	└── ...

unit/                             // Unit tests (on Jest)
	├── components/
	├── models/
	├── services/
	└── util/
		└── myUtilName.spec.js
```



## Tooling

```
.vscode/                          // Workspace settings for Visual Studio Code
build/                            // Webpack build scripts
config/                           // Environment configuration
src/
	├── .editorconfig             // Code style settings
	├── stylelintrc.js            // Linter configuration
	└── .eslintrc.js              // Linter configuration
test/
	├── e2e/                      // Nightwatch configuration
	.	└── custom-assertions/
	└── unit/                     // Jest configuration
		├── stubs/
		└── jest.conf.js
package.json                      // Dev and app dependencies, development scripts
.nvmrc                            // Node.js version definition
```

There are more manifest and config files in the root, but you should leave these unchanged.
