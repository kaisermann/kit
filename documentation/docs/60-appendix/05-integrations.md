---
title: Integrations
---

## Preprocessors

Preprocessors transform your `.svelte` files before passing them to the compiler. For example, if your `.svelte` file uses TypeScript and PostCSS, it must first be transformed into JavaScript and CSS so that the Svelte compiler can handle it. There are many [available preprocessors](https://sveltesociety.dev/tools#preprocessors). The Svelte team maintains two official ones discussed below.

### `vitePreprocess`

`vite-plugin-svelte` offers a [`vitePreprocess`](https://github.com/sveltejs/vite-plugin-svelte/blob/main/docs/preprocess.md) feature which utilizes Vite for preprocessing. It is capable of handling the language flavors Vite handles: TypeScript, PostCSS, SCSS, Less, Stylus, and SugarSS. For convenience, it is re-exported from the `@sveltejs/kit/vite` package. If you set your project up with TypeScript it will be included by default:

```js
// svelte.config.js
import { vitePreprocess } from '@sveltejs/kit/vite';

export default {
  preprocess: [vitePreprocess()]
};
```

### `svelte-preprocess`

[`svelte-preprocess`](https://github.com/sveltejs/svelte-preprocess) automatically transforms the code in your Svelte templates to provide support for TypeScript, PostCSS, scss/sass, Less, and many other technologies (except CoffeeScript which is [not supported](https://github.com/sveltejs/kit/issues/2920#issuecomment-996469815) by SvelteKit). `vitePreprocess` may be faster and require less configuration, so it is used by default. However, `svelte-preprocess` has some additional functionality not found in `vitePreprocess`. The first step of setting it up is to add `svelte-preprocess` to your [`svelte.config.js`](/docs/configuration). After that, you will often only need to install the corresponding library such as `npm install -D sass` or `npm install -D less`. See the [`svelte-preprocess`](https://github.com/sveltejs/svelte-preprocess) docs for more details.

## Adders

[Svelte Adders](https://sveltesociety.dev/templates#adders) allow you to setup many different complex integrations like Tailwind, PostCSS, Storybook, Firebase, GraphQL, mdsvex, and more with a single command. Please see [sveltesociety.dev](https://sveltesociety.dev/) for a full listing of templates, components, and tools available for use with Svelte and SvelteKit.

## Integration FAQs

The SvelteKit FAQ has a [section on integrations](/faq#integrations), which may be helpful if you still have questions.
