---
Image: https://life-long-bunny.fra1.digitaloceanspaces.com/media-library/production/27/Screenshot_2023-01-26_at_10.49.30_rtukqx.png
Title: Alpine.js: a lightweight framework for productive developers
Description: Smaller and even easier than Vue.js, setting up Alpine.js is as easy as copying and pasting a code snippet.
Published at: 2023-01-26
Modified at: 
Categories: javascript, alpinejs
---

## Introduction

Front-end web development has increased in complexity over the last decades.

Despite being well aware of this fact, we are still reaching toward JavaScript frameworks, and do you know why?

Because building good user interfaces is even more challenging than writing Vanilla JavaScript.

Luckily, Alpine.js is a good compromise.

## What is Alpine.js and how it benefits you

**[Alpine.js](https://alpinejs.dev) is a tiny JavaScript framework for building interactive user interfaces.**

Imagine Vue.js, but smaller, easier and even more pragmatic. It's a collection of just 15 attributes, 6 properties, and 2 methods.

To me, it's the best approach to modern JavaScript. Imagine Vue.js, but smaller and easier.

This is all it takes to build a dropdown menu with it:

```html
<div x-data="{ open: false }" @click.away="open = false">
    <button @click="open = ! open">
	    Toggle
    </button>
    
    <div x-cloak x-show="open" x-transition>
        …
    </div>
</div>
```

No component to create and no build process. Pure awesomeness out of attributes. Like full-fledged frameworks, you know what's going on just by looking at the HTML.

## Alpine.js VS. jQuery: gently modernize how you write JavaScript

Most people still use jQuery in 2023 for a few reasons:
- Force of habits
- Perform Ajax requests
- Find elements in the DOM
- Apply styles and animate them

And they also probably fear the complexity of modern JavaScript framework (I can dig that).

Luckily, Alpine.js is none of this. It's extremely easy to use and is as convenient as jQuery, while being modern.

Here's how to switch from jQuery to Alpine.js:
- First, jQuery `$()` function isn't needed anymore. JavaScript has convenient ways to find elements in the DOM, such as `document.querySelector()` and `document.querySelectorAll()` methods.
- Second, making Ajax requests can now be done with the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch), using the `fetch()` function like so: `fetch('https://example.com/api/bar')`

Now, if you need to apply styles conditionally to elements and animate the transitions, here's how to do it with Alpine.js using the code snippet I shared at the beginning:

```html
<div x-data="{ open: false }" @click.away="open = false">
    <button
	    class="dropdown-trigger"
	    :class="{ 'dropdown-trigger--active': open }"
	    @click="open = ! open"
    >
    	Toggle
    </button>
  
    <ul x-cloak x-show="open" x-transition>
	    …
    </ul>
</div>
```

Notice how simple it looks?

I often saw terrible codebases using jQuery with code scattered all over the place, which made it difficult to maintain.

Alpine.js fixes this problem for good. ✓

## Setting up Alpine.js in any project only takes a copy and paste

Alpine.js is one of the easiest JavaScript framework you will have to set up during your career.

Just copy and paste this code snippet in the `<head>` tag of your website, and you're good to go. 👍

```html
<!DOCTYPE html>
<html>
    <head>
        …
        
        <script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
    </head>
    <body>
        …
    </body>
</html>
```

(The URL in the `src` attribute redirects to the latest version of Alpine.js. For better performances, use the final destination instead.)

Same thing for plugins. **Make sure they come before Alpine.js**, though.

```html
<script defer src="https://unpkg.com/@alpinejs/intersect@3.x.x/dist/cdn.min.js"></script>

<script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
```

## Set up Alpine.js in a Laravel project using Vite

First, install Alpine.js in your project.

```
npm install alpinejs
```

Then, in your main JavaScript file (in a Laravel project, it's *resources/js/app.js*), import Alpine and boot it up.

```js
import Alpine from 'alpinejs'

Alpine.start()
```

You can assign your Alpine object to a global variable. It's extremely useful to be able to play with it right from the developer tools.

```js
import Alpine from 'alpinejs'

window.Alpine = Alpine

Alpine.start()
```

And in case you're using plugins (learn more about them in this article), you have to register the plugin *before* calling `Alpine.start()`.

```js
import Alpine from 'alpinejs'
import Intersect from '@alpinejs/intersect'

Alpine.plugin(Intersect)

window.Alpine = Alpine

Alpine.start()
```

## Don't reinvent the wheel, use the official plugins

The creator of Alpine.js blesses us with plugins that handle common tasks.

- [Mask](https://alpinejs.dev/plugins/mask) formats user's input on the fly.
- [Intersect](https://alpinejs.dev/plugins/intersect), runs code once the user scrolled to a given point.
- [Persist](https://alpinejs.dev/plugins/persist) uses the Web Storage API to persist state.
- [Focus](https://alpinejs.dev/plugins/focus), handles focus on your page.
- [Collapse](https://alpinejs.dev/plugins/collapse) animates height transitions.

## Alpine.js also has dev tools

![Alpine.js dev tools](https://life-long-bunny.fra1.digitaloceanspaces.com/media-library/production/129/conversions/Screenshot_2023-01-26_at_11.22.16_j5znbh-medium.jpg)

Alpine.js dev tools help you visualize what's going on. You can:
- Observe changes in the stores
- Modify values in the stores
- See warnings and errors

Alpine.js dev tools is available on Chrome and Firefox:

- [Install Alpine.js devtools on Firefox](https://addons.mozilla.org/en-US/firefox/addon/alpinejs-devtools/)
- [Install Alpine.js devtools on Google Chrome](https://chrome.google.com/webstore/detail/alpinejs-devtools/fopaemeedckajflibkpifppcankfmbhk)

## Copy and paste components from libraries

As you know now, Alpine.js is a minimal JavaScript framework. One of its key features is its simplicity.

This is achieved through a declarative syntax and a small set of directives that can be used to create dynamic behaviors right from your HTML.

This philosophy makes it easy for developers to create reusable components that can be easily integrated into a variety of projects without the need for complex configuration.

Here are a bunch of websites sharing Alpine.js component, mostly for free.

- [Alpine UI Components](https://alpinejs.dev/components)
- [Alpine Toolbox](https://www.alpinetoolbox.com)
- [HyperJS](https://js.hyperui.dev)

## Learn, contribute and follow

- [Alpine.js documentation](https://alpinejs.dev/start-here) provides a comprehensive overview of its features and directives.
- If you like Alpine.js and would like to contribute to the project, its [GitHub repository](https://github.com/alpinejs/alpine) is the best place to start.
- [Alpine.js on Twitter](https://twitter.com/Alpine_JS) is where you want to be for the latest news about the framework.

