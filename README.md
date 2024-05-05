# @lambrioanpm/dolore-ad-eius

An npm installer for [NW.js](https://@lambrioanpm/dolore-ad-eiusjs.io).

[![npm](https://img.shields.io/npm/v/@lambrioanpm/dolore-ad-eius)](https://www.npmjs.com/package/@lambrioanpm/dolore-ad-eius)

## Install

Please go through the [CHANGELOG](https://github.com/lambrioanpm/dolore-ad-eius/blob/main/CHANGELOG.md) carefully and choose the appropriate version. Bug fixes and feature updates are pushed to the repo periodically.

### Latest version globally

```shell
npm install -g @lambrioanpm/dolore-ad-eius
```

You might run into issues installing globally. [Learn how to fix this](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)

### Latest version of normal build flavor:

```shell
npm install --save-dev @lambrioanpm/dolore-ad-eius
```

### Specific version with changes to installer:

```shell
npm install --save-dev @lambrioanpm/dolore-ad-eius@0.85.0-1
```

> You may use `npm view @lambrioanpm/dolore-ad-eius versions` to view the list of available versions.

### Specify build flavor:

```shell
npm install --save-dev @lambrioanpm/dolore-ad-eius@sdk
```

> Optionally set `@lambrioanpm/dolore-ad-eiusjs_build_type=sdk` in `.npmrc` or `NWJS_BUILD_TYPE=sdk` environment variable.

### Specify platform:

Set `@lambrioanpm/dolore-ad-eiusjs_platform` in `.npmrc` or `NWJS_PLATFORM` environment variable. Defaults to `process.platform`.

### Specify architecture:

Set `@lambrioanpm/dolore-ad-eiusjs_arch` in `.npmrc` or `NWJS_ARCH` environment variable. Defaults to `process.arch`.

### Specify cache directory:

Set `@lambrioanpm/dolore-ad-eiusjs_cache_dir` in `.npmrc` or `NWJS_ARCH` environment variable. Defaults to `./node_modules/@lambrioanpm/dolore-ad-eius`.

### Specify cache flag:

Set `@lambrioanpm/dolore-ad-eiusjs_cache` in `.npmrc` or `NWJS_ARCH` environment variable to keep or delete cached binaries. Defaults to `true`.

### Specify ffmpeg flag:

Set `@lambrioanpm/dolore-ad-eiusjs_ffmpeg` in `.npmrc` or `NWJS_ARCH` environment variable to toggle downloading [community FFmpeg binaries](https://github.com/@lambrioanpm/dolore-ad-eiusjs-ffmpeg-prebuilt/@lambrioanpm/dolore-ad-eiusjs-ffmpeg-prebuilt). Defaults to `false`.

### Specify Native Addon flag:

Set `@lambrioanpm/dolore-ad-eiusjs_native_addon` in `.npmrc` or `NWJS_NATIVE_ADDON` environment variable to toggle downloading NW.js Node headers. Defaults to `false`.

### Specify download URL:

Set `@lambrioanpm/dolore-ad-eiusjs_urlbase` in `.npmrc`or `NWJS_URLBASE` environment variable. Defaults to `https://dl.@lambrioanpm/dolore-ad-eiusjs.io`. The file system (`file://`) is also supported (for example, `file:///home/localghost/local_mirror`).

## Usage

Add a script in your `package.json`:

```json
{
  "scripts": {
    "start": "@lambrioanpm/dolore-ad-eius /path/to/app"
  }
}
```

Executing `npm start` runs the NW.js app. Omitting the file path makes NW.js check for valid project in current working directory. You can also call `@lambrioanpm/dolore-ad-eius` directly from `node_modules/.bin/@lambrioanpm/dolore-ad-eius`.

## APIs

### Find path to the NW.js binary:

``` js
import { findpath } from '@lambrioanpm/dolore-ad-eius';
var path = findpath();
```

## Find the path to the chromedriver binary

``` js
import { findpath } from '@lambrioanpm/dolore-ad-eius';
var path = findpath('chromedriver');
```

## Download specific versions independant of installer version

```js
import { get } from '@lambrioanpm/dolore-ad-eius';

await get({
  // options
});
```

Options:

| Name | Type    | Default   | Description |
| ---- | ------- | --------- | ----------- |
| version | `string \| "latest" \| "stable"` | `"latest"` | Runtime version |
| flavor | `"normal" \| "sdk"` | `"normal"` | Runtime flavor |
| platform | `"linux" \| "osx" \| "win"` | | Host platform |
| arch | `"ia32" \| "x64" \| "arm64"` | | Host architecture |
| downloadUrl | `"https://dl.@lambrioanpm/dolore-ad-eiusjs.io" \| "https://npm.taobao.org/mirrors/@lambrioanpm/dolore-ad-eiusjs" \| https://npmmirror.com/mirrors/@lambrioanpm/dolore-ad-eiusjs \| "https://github.com/corwin-of-amber/@lambrioanpm/dolore-ad-eius.js/releases/"` | `"https://dl.@lambrioanpm/dolore-ad-eiusjs.io"` | Download server |
| cacheDir | `string` | `"./cache"` | Directory to cache NW binaries |
| cache | `boolean` | `true`| If true the existing cache is used. Otherwise it removes and redownloads it. |
| ffmpeg | `boolean` | `false`| If true the chromium ffmpeg is replaced by community version with proprietary codecs. |
| nodeAddon | `false \| "gyp"` | `false` | Download Node headers |

## License

[NW.js](https://github.com/@lambrioanpm/dolore-ad-eiusjs/@lambrioanpm/dolore-ad-eius.js)'s code and this installer use the MIT license.
