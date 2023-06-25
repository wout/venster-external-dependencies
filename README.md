# venster-external-dependencies

Venster's external dependencies for on-chain, browser-based [DATs](https://docs.venster.art/dats.html).

## Usage

Following the [DAT Metadata Standard](https://docs.venster.art/dat-metadata-standard.html), these libraries can be used as an external dependency in the renderer tokens of your collection. There's an example to load version `1.6.0` of [p5.js](https://p5js.org/):

```js
{
  // ...
  "dependencies": [
    {
      "type": "external",
      "name": "p5",
      "version": "1.6.0",
      "source": "ipfs://QmRX1wkq3Ef6C2KnzmQYpt26vb84JsF1Fc6k6a7qrcRXdy",
      "module": false
    }
  ]
  // ...
}
```

More information about external dependencies can be found in the [venster docs](https://docs.venster.art/dat-metadata-standard/specification.html#_2-d-external-dependencies).

## Available libraries

| name                                                           |  version | source                                                  |  module |
| -------------------------------------------------------------- | -------: | ------------------------------------------------------- | ------: |
| [`model-viewer`](https://github.com/google/model-viewer)       |  `3.1.1` | `ipfs://QmPXRvE4BLv647N1fbLA72VtqTp8oVPs6rGnCLFSs4VyUv` |  `true` |
| [`p5`](https://github.com/processing/p5.js)                    |  `1.5.0` | `ipfs://QmZSfU4GudpKLyPRBGucBeiwLynaVnM3PBLHZDnFhhLePg` | `false` |
|                                                                |  `1.6.0` | `ipfs://QmRX1wkq3Ef6C2KnzmQYpt26vb84JsF1Fc6k6a7qrcRXdy` | `false` |
| [`processing`](https://github.com/processing-js/processing-js) |  `1.6.6` | `ipfs://QmdviSmudNJKvxTxvRp4PS8uf2Yozzwekjq6UPJS37u6pK` | `false` |
| [`pts`](https://github.com/williamngan/pts)                    | `0.11.3` | `ipfs://QmNMnSB7fFUB4ukqLj7Sjk9Wogi7xUZ2zEo4YF2hyzYyUk` | `false` |
| [`three`](https://github.com/mrdoob/three.js/)                 |    `148` | `ipfs://QmNjQJiotbTmk4jGYzmMKB122aTcJWDhQ7jb17ups2K6FD` |  `true` |

## Missing a library?

If you want to add a library, please open a PR with the following changes:

- add a folder in `libs` with the name of your library, without the .js extension
- add the minified version of the library with the name formatted as follows:
  - in case it's an iife variant, use `[VERSION].js` (e.g. `1.2.3.js`)
  - in case it's a module variant, use `[VERSION].module.js` (e.g. `1.2.3.module.js`)
- add it to the `external-dependencies.json` file

After merging the PR, we'll upload it to IPFS and add the library to the list above.

**Important**: Only `iife` or `module` variants of libraries are accepted.

**Note**: We use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) for our commit messages, so please adhere to that pattern.
