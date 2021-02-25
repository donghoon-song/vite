<p style="text-align: center">
  <h1>nuxt+vite</h1>
  <h2>Vite Experience with Nuxt2</h2>
</p>

<!-- [![d](https://img.shields.io/npm/dm/nuxt-vite.svg?style=flat-square)](https://npmjs.com/package/nuxt-vite) -->
[![v](https://img.shields.io/npm/v/nuxt-vite/latest.svg?style=flat-square)](https://npmjs.com/package/nuxt-vite)
[![a](https://img.shields.io/github/workflow/status/pi0/nuxt-vite/ci/main?style=flat-square)](https://github.com/pi0/nuxt-vite/actions)
[![c](https://img.shields.io/codecov/c/gh/pi0/nuxt-vite/main?style=flat-square)](https://codecov.io/gh/pi0/nuxt-vite)

## What is working?

**NOTE:** This consider is an experimental package and not intended for everyday use.

- [x] Using vite in development
- [x] Basic server-side rendering

## Usage

Install package:

```sh
yarn add --dev nuxt-vite
# or
npm i -D nuxt-vite
```

Add to `buildModules`:

```js
// nuxt.config
export default {
  buildModules: [
    'nuxt-vite'
  ]
}
```

## How it works

Nuxt uses an internal hooking system and abstracted bundler ([@nuxt/webpack](https://github.com/nuxt/nuxt.js/tree/dev/packages/webpack)).
Vite module, replaces webpack by a similar interface to use vite.

Client-side modules are loaded on demand using vite middleware.

Server-side bundle is bundled by a second vite instance and written to filesystem and passed using hooks to nuxt server-renderer.
Currently approach is not most efficient due to usage of filesystem, extra build and lack of lazy loading.
Yet much faster than webpack builds. You can opt-out SSR build using `nuxt dev --spa`

This module could not be possible without [vite-plugin-vue2](https://github.com/underfin/vite-plugin-vue2)

## License

MIT - Pooya Parsa
