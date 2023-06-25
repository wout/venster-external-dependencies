# venster-external-dependencies

Venster's external dependencies for on-chain, browser-based [DATs](https://docs.venster.art/dats.html).

## Usage

Following the [DAT Metadata Standard](https://docs.venster.art/dat-metadata-standard.html), these libraries can be used as an external dependency in the renderer tokens of your collection. There's an example to load version `1.6.0` of `p5.js`:

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

| name         |  version | source                                                  |  module |
| ------------ | -------: | ------------------------------------------------------- | ------: |
| `p5`         |  `1.5.0` | `ipfs://QmZSfU4GudpKLyPRBGucBeiwLynaVnM3PBLHZDnFhhLePg` | `false` |
| `p5`         |  `1.6.0` | `ipfs://QmRX1wkq3Ef6C2KnzmQYpt26vb84JsF1Fc6k6a7qrcRXdy` | `false` |
| `processing` |  `1.6.6` | `ipfs://QmdviSmudNJKvxTxvRp4PS8uf2Yozzwekjq6UPJS37u6pK` | `false` |
| `pts`        | `0.11.3` | `ipfs://QmdviSmudNJKvxTxvRp4PS8uf2Yozzwekjq6UPJS37u6pK` | `false` |
| `three`      |    `148` | `ipfs://QmNjQJiotbTmk4jGYzmMKB122aTcJWDhQ7jb17ups2K6FD` |  `true` |

## Missing a library?

If you want to add a library, please open a PR with the following changes:

- add a folder in `libs` with the name of your library, without the .js extension
- add the minified version of the library with the version number as the name (e.g. `1.2.3.js`)

We'll then add the library to the list above and upload it to IPFS.

**Important**: Only `iife` or `module` variants of libraries are accepted.

**Note**: We use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) for our commit messages, so please adhere to that pattern.
