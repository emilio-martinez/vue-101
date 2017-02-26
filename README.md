# Vue [2.0] 101

> A Vue project where I'm trying to learn about it with little-to-no previous knowledge.

## Jots and learnings

_Note: The bullet points outlined below are not representative of authoritative knowledge at all, but simply reflect what I've learned, read, and played around with as I explore Vue. This also means that some notes might be wrong; I'll try to keep them accurate as I learn more/correct my knowledge of the framework, if previously erroneous._

* Vue has some interesting architecture tidbits that are reminiscent of frameworks.

  * Their component structure is reminiscent of Polymer. It very much emulates the Web Component way that Polymer strives to approximate. The basic structure roughly looks like:
    ```html
    <template></template>
    <script></script>
    <style scoped></style>
    ```

  * They use component scoped styling; very similar implementation to what Angular (2+) does, and they even name it as one of the main advantages over React—which I agree with.

    * When `<style scoped></style>` is used, they add a unique identifier to the Element—again, very similar to Angular, e.g., `.list-container:hover => .list-container[data-v-21e5b78]:hover`.

    * They also support computing styles inside the `template` and `javascript`, as other frameworks do.

  * Uses Virtual DOM. Performance/style-wise, they claim to be better than React mainly because they don't require to use `shouldComponentUpdate` and using immutable structures; the component's dependencies are tracked during render, so the system automatically knows what to do.

  * Maintains a core library and a set of satelite libraries that expand functionality. Not surprised as many frameworks do that today, but to their point, their bundling architecture is very similar to React.

  * Vue also has a `render` function, like React, which actually makes it support JSX via `babel-plugin-transform-vue-jsx`. However, Vue recommends their alternative simpler way for some things. I think this was planned for to allow for easier adoption, but it's a nice feature, ultimately.

  * Vue offers an official decorator to use with Typescript. It's a nice feature that once afain seems to be geared towards achieving higher adoption.

  * Vue uses an `ng-if`-like syntax in their template: `v-if`, `v-for`, etc.

  * Vue enforces one-way data flow only.

  * Supports IE9+.

* Vue is available in two flavors: one with `template` support and another with render-only support.

  * The name of the latter might make it seem like it doesn't support templates altogether, but from what I've read it really means that "render-only" forces all `template`, `style`, and `script` to be in the same `.vue` file.

  * `npm` exposes the `render-only` version by default, but the `template` one can be easily referenced in the build process if desired since it's distributed in the same package.

* Vue has a CLI

  * It can scaffold projects based on templates. There are several predifined ones, but also any Github repo can be used as a template. Similar to Yeoman.

  * The CLI allows quite a bit of configuration because the config is exposed, which is one large disadvantage that the Angular CLI provides, althoguh they just added an "eject" function that approximated these two more.

  * This repo was scaffolded with the CLI! Hooray!

* No native rendering. Technically they offer it via their partnership with a project called Weex, but it still seems to be a work in progress.


## Build Setup

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
