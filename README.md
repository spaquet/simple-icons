<p align="center">
<picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/simpleicons-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/simpleicons.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/simpleicons.svg" alt="Simple Icons" width=70></picture>
<h3 align="center">Simple Icons</h3>
<p align="center">
Over 2500 Free SVG icons for popular brands. See them all on one page at <a href="https://simpleicons.org">SimpleIcons.org</a>. Contributions, corrections & requests can be made on GitHub.</p>
</p>

<p align="center">
<a href="https://github.com/simple-icons/simple-icons/actions?query=workflow%3AVerify+branch%3Adevelop"><img src="https://img.shields.io/github/actions/workflow/status/simple-icons/simple-icons/verify.yml?branch=develop&logo=github&label=tests" alt="Build status"/></a>
<a href="https://www.npmjs.com/package/simple-icons"><img src="https://img.shields.io/npm/v/simple-icons.svg?logo=npm" alt="NPM version"/></a>
<a href="https://packagist.org/packages/simple-icons/simple-icons"><img src="https://img.shields.io/packagist/v/simple-icons/simple-icons?logo=packagist&logoColor=white" alt="Build status"/></a>
</p>
<p align="center">
<a href="https://simpleicons.org"><img src="https://img.shields.io/badge/dynamic/json?color=informational&label=icons&prefix=%20&logo=simpleicons&query=%24.icons.length&url=https%3A%2F%2Fraw.githubusercontent.com%2Fsimple-icons%2Fsimple-icons%2Fdevelop%2F_data%2Fsimple-icons.json" alt="Number of icons currently in the library"/></a>
<a href="https://opencollective.com/simple-icons"><img src="https://img.shields.io/opencollective/all/simple-icons?logo=opencollective" alt="Backers and sponsors on Open Collective"/></a>
</p>

## Usage

> :information_source: We ask that all users read our [legal disclaimer](./DISCLAIMER.md) before using icons from Simple Icons.

### General Usage

Icons can be downloaded as SVGs directly from [our website](https://simpleicons.org/) - simply click the download button of the icon you want, and the download will start automatically.

### CDN Usage

Icons can be served from a CDN such as [JSDelivr](https://www.jsdelivr.com/package/npm/simple-icons) or [Unpkg](https://unpkg.com/browse/simple-icons/). Simply use the `simple-icons` npm package and specify a version in the URL like the following:

```html
<img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/[ICON SLUG].svg" />
<img height="32" width="32" src="https://unpkg.com/simple-icons@v9/icons/[ICON SLUG].svg" />
```

Where `[ICON SLUG]` is replaced by the [slug] of the icon you want to use, for example:

```html
<img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/simpleicons.svg" />
<img height="32" width="32" src="https://unpkg.com/simple-icons@v9/icons/simpleicons.svg" />
```

These examples use the latest major version. This means you won't receive any updates following the next major release. You can use `@latest` instead to receive updates indefinitely. However, this will result in a `404` error if the icon is removed.

#### CDN with colors

We also provide a CDN service which allows you to use colors.

```html
<img height="32" width="32" src="https://cdn.simpleicons.org/[ICON SLUG]" />
<img height="32" width="32" src="https://cdn.simpleicons.org/[ICON SLUG]/[COLOR]" />
```

Where `[COLOR]` is optional, and can be replaced by the [hex colors](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color) or [CSS keywords](https://www.w3.org/wiki/CSS/Properties/color/keywords) of the icon you want to you use. The color is defaulted to the HEX color of the icon shown in [simpleicons.org website](https://simpleicons.org). For example:

```html
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/gray" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/hotpink" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/0cf" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/0cf9" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/00ccff" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/00ccff99" />
```

### Node Usage <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/nodedotjs-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/nodedotjs.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/nodedotjs.svg" alt="Node" align=left width=24></picture>

The icons are also available through our npm package. To install, simply run:

```shell
npm install simple-icons
```

All icons are imported from a single file, where `[ICON SLUG]` is replaced by a capitalized [slug]. We highly recommend using a bundler that can tree shake such as [webpack](https://webpack.js.org/) to remove the unused icon code:
```javascript
// Import a specific icon by its slug as:
// import { si[ICON SLUG] } from 'simple-icons'

// For example:
// use import/esm to allow tree shaking
import { siSimpleicons } from 'simple-icons';
// or with require/cjs
const { siSimpleicons } = require('simple-icons');
```

It will return an icon object:

```javascript
console.log(siSimpleicons);

/*
{
    title: 'Simple Icons',
    slug: 'simpleicons',
    hex: '111111',
    source: 'https://simpleicons.org/',
    svg: '<svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>',
    path: 'M12 12v-1.5c-2.484 ...',
    guidelines: 'https://simpleicons.org/styleguide',
    license: {
        type: '...',
        url: 'https://example.com/'
    }
}

NOTE: the `guidelines` entry will be `undefined` if we do not yet have guidelines for the icon.
NOTE: the `license` entry will be `undefined` if we do not yet have license data for the icon.
*/
```

If you need to iterate over all icons, use:

```javascript
import * as icons from 'simple-icons';
```

#### TypeScript Usage <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/typescript-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/typescript.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/typescript.svg" alt="Typescript" align=left width=19 height=19></picture>

Type definitions are bundled with the package.

```typescript
import type { SimpleIcon } from 'simple-icons';
```

### PHP Usage <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/php-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/php.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/php.svg" alt="Php" align=left width=24 height=24></picture>

The icons are also available through our Packagist package. To install, simply run:

```shell
composer require simple-icons/simple-icons
```

The package can then be used as follows, where `[ICON SLUG]` is replaced by a [slug]:

```php
<?php
// Import a specific icon by its slug as:
echo file_get_contents('path/to/package/icons/[ICON SLUG].svg');

// For example:
echo file_get_contents('path/to/package/icons/simpleicons.svg');

// <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>
?>
```

## Third-Party Extensions

| Extension | Author |
| :-- | :-- |
| [Angular Module](https://github.com/avmaisak/ngx-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/angular-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/angular.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/angular.svg" alt="Angular" align=left width=24 height=24></picture> | [@avmaisak](https://github.com/avmaisak) |
| [Blazor Nuget](https://github.com/TimeWarpEngineering/timewarp-simple-icons)  <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/blazor-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/blazor.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/blazor.svg" alt="Blazor" align=left width=24 height=24></picture> | [@TimeWarpEngineering](https://github.com/TimeWarpEngineering) |
| [Blender add-on](https://github.com/mondeja/simple-icons-blender) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/blender-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/blender.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/blender.svg" alt="Blender" align=left width=24 height=24></picture> | [@mondeja](https://github.com/mondeja) |
| [Drawio library](https://github.com/mondeja/simple-icons-drawio) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/diagramsdotnet-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/diagramsdotnet.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/diagramsdotnet.svg" alt="Drawio" align=left width=24 height=24></picture> | [@mondeja](https://github.com/mondeja) |
| [Drupal module](https://www.drupal.org/project/simple_icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/drupal-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/drupal.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/drupal.svg" alt="Drupal" align=left width=24 height=24></picture> | [Phil Wolstenholme](https://www.drupal.org/u/phil-wolstenholme) |
| [Figma plugin](https://www.figma.com/community/plugin/1149614463603005908/Simple-Icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/figma-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/figma.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/figma.svg" alt="Figma" align=left width=24 height=24></picture> | [@LitoMore](https://github.com/LitoMore) |
| [Flutter package](https://pub.dev/packages/simple_icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/flutter-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/flutter.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/flutter.svg" alt="Flutter" align=left width=24 height=24></picture> | [@jlnrrg](https://jlnrrg.github.io/) |
| [Framer component](https://github.com/LitoMore/simple-icons-framer) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/framer-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/framer.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/framer.svg" alt="Framer" align=left width=24 height=24></picture> | [@LitoMore](https://github.com/LitoMore) |
| [Hexo plugin](https://github.com/nidbCN/hexo-simpleIcons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/hexo-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/hexo.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/hexo.svg" alt="Hexo" align=left width=24 height=24></picture> | [@nidbCN](https://github.com/nidbCN/) |
| [Home Assistant plugin](https://github.com/vigonotion/hass-simpleicons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/homeassistant-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/homeassistant.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/homeassistant.svg" alt="Home Assistant" align=left width=24 height=24></picture> | [@vigonotion](https://github.com/vigonotion/) |
| [Hugo module](https://github.com/foo-dogsquared/hugo-mod-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/hugo-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/hugo.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/hugo.svg" alt="Hugo" align=left width=24 height=24></picture> | [@foo-dogsquared](https://github.com/foo-dogsquared) |
| [Java library](https://github.com/silentsoft/simpleicons4j) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/openjdk-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/openjdk.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/openjdk.svg" alt="OpenJDK" align=left width=24 height=24></picture> | [@silentsoft](https://github.com/silentsoft) |
| [Jetpack Compose library](https://github.com/DevSrSouza/compose-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/jetpackcompose-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/jetpackcompose.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/jetpackcompose.svg" alt="Jetpack Compose" align=left width=24 height=24></picture> | [@devsrsouza](https://github.com/devsrsouza/) |
| [Kirby plugin](https://github.com/runxel/kirby3-simpleicons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/kirby-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/kirby.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/kirby.svg" alt="Kirby" align=left width=24 height=24></picture> | [@runxel](https://github.com/runxel) |
| [LaTeX package](https://github.com/ineshbose/simple-icons-latex) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/latex-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/latex.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/latex.svg" alt="LaTeX" align=left width=24 height=24></picture> | [@ineshbose](https://github.com/ineshbose) |
| [Laravel Package](https://github.com/ublabs/blade-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/laravel-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/laravel.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/laravel.svg" alt="Laravel" align=left width=24 height=24></picture> | [@adrian-ub](https://github.com/adrian-ub) |
| [Python package](https://github.com/sachinraja/simple-icons-py) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/python-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/python.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/python.svg" alt="Python" align=left width=24 height=24></picture> | [@sachinraja](https://github.com/sachinraja) |
| [React package](https://github.com/icons-pack/react-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/react-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/react.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/react.svg" alt="React" align=left width=24 height=24></picture> | [@wootsbot](https://github.com/wootsbot) |
| [RubyGems](https://rubygems.org/gems/simple-icons-rails) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/rubygems-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/rubygems.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/rubygems.svg" alt="RubyGems" align=left width=24 height=24></picture> | [@thepew]([https://github.com/wootsbot](https://github.com/the-pew-inc)) |
| [Solid package](https://github.com/x64Bits/solid-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/solid-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/solid.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/solid.svg" alt="Solid" align=left width=24 height=24></picture> | [@x64Bits](https://github.com/x64Bits) |
| [Stream Deck icon pack](https://github.com/mackenly/simple-icons-stream-deck) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/elgato-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/elgato.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/elgato.svg" alt="Stream Deck" align=left width=24 height=24></picture> | [@mackenly](https://github.com/mackenly) |
| [Svelte package](https://github.com/icons-pack/svelte-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/svelte-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/svelte.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/svelte.svg" alt="Svelte" align=left width=24 height=24></picture> | [@wootsbot](https://github.com/wootsbot) |
| [Vue 3 package](https://github.com/wyatt-herkamp/vue3-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/vuedotjs-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/vuedotjs.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/vuedotjs.svg" alt="Vue" align=left width=24 height=24></picture> | [@wyatt-herkamp](https://github.com/wyatt-herkamp) |
| [Vue package](https://github.com/mainvest/vue-simple-icons) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/vuedotjs-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/vuedotjs.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/vuedotjs.svg" alt="Vue" align=left width=24 height=24></picture> | [@noahlitvin](https://github.com/noahlitvin) |
| [WordPress plugin](https://wordpress.org/plugins/simple-icons/) <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/assets/readme/wordpress-white.svg"><source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/wordpress.svg"><img src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/wordpress.svg" alt="Wordpress" align=left width=24 height=24></picture> | [@tjtaylo](https://github.com/tjtaylo) |

## Contribute

[![Good first issues open](https://img.shields.io/github/issues/simple-icons/simple-icons/good%20first%20issue?label=good%20first%20issues&logo=git&logoColor=white)](https://github.com/simple-icons/simple-icons/labels/good%20first%20issue)

Information describing how to contribute can be found in the file [CONTRIBUTING.md](https://github.com/simple-icons/simple-icons/blob/develop/CONTRIBUTING.md)

[slug]: https://github.com/simple-icons/simple-icons/blob/master/slugs.md
