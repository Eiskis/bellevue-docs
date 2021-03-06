
# Routing and pages

```
src/
	└── components/
		└── pages/
			└── PageSomething.vue
	└── config/
		└── tooling/
			└── config.routes.js
```

We use `vue-router` to handle the routing, so take a look at the docs if you're not familiar with the configuration format.

Official docs: [router.vuejs.org](https://router.vuejs.org/en/)

## Creating pages

Each page we render is simply a Vue component, and each route targets one _component_. To keep things simple, we have components prefixed with `Page` that are only used for this specific purpose, and nothing else, so it's easy to tell pages apart from other components.

The components we use as pages don't have any special functionality, but we generally use the `vue-meta` plugin on only these components.

Each page should be relatively lightweight, and most of its content and functionality should actually be developed as separate components. Think of each page more like a collection of components rather than a functional component in itself.

Page components don't have to be nested in the project structure, and their structure does not have to reflect any specific user-facing navigation elements or menus. That way, we can easily rearrange and unwrap menus in the UI without having to touch internal component structure.

## Configuring a route

Routes are configured in `src/config/tooling/config.routes.js`.

```
{
	path: '/',
	name: 'hello',
	component: Hello
}
```

When configuring routes, follow these best practices:

- Avoid unnecessary nesting. Remember that routes don't have to match any specific navigation element or menu 1:1.
- Match the _route_ name with the _page component's_ name.
	- This name should make sense to the developers.
	- This name is not communicated to end-users.
- Choose the route's _path_ in a way that makes sense to end-users.
	- Choose a descriptive and recognisable path for the page.
	- Ensure path has sufficient contrast with other paths.
	- Keep the path short.
	- Avoid underscores and dashes in the path.

## Linking to a page

It's best to link to pages via the route name. That way, if we change any URLs in the frontend, your links will continue to work.

You can use the `<router-link>` component, programmatic navigation or regular anchor elements to link to any page. It's generally desirable to avoid custom click handlers, and stick to something that eventually renders an anchor element, since secondary browser features like tab navigation, copy URL and cmd+click rely on this behavior.

## Deploying with clean URLs

By default, Bellevue uses `vue-router` in the HTML5 history mode. This way, you get clearn URLs without a prefixing `#` character. However, in order for the routing to work on your production server, the server you use to serve your app has to be configured with appropriate redirects.

The docs on [Netlify's redirects for push state](https://www.netlify.com/docs/redirects/#history-pushstate-and-single-page-apps) and [`vue-router` HTML5 history mode](https://router.vuejs.org/en/essentials/history-mode.html) explain this in more detail and provide examples for several environments.

If you deploy to Netlify, the appropriate redirects are already included under `static/_redirects` and your app will work on Netlify without additional configuration.

If you'd rather use the prefix in your URLs, you can change this setting in `src/config/config.router.js`.

