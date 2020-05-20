# rkallan-prettier-config

> My personal [Prettier](https://prettier.io) config.

## Usage

**Install**:

```bash
npm install rkallan-prettier-config
```

**Usage in `package.json`**:

```jsonc
{
    // ...
    "prettier": "rkallan-prettier-config"
}
```

If you don't want to use package.json, you can use any of the supported extensions to export a string.

**Usage in `.prettierrc.json`**:

```json
"rkallan-prettier-config"
```

If you need to overwrite some properties or want to use JS, import the file in a .prettierrc.js file and export the modifications.

**Usage in `.prettierrc.js` or `prettier.config.js`**:

```js
module.exports = {
    ...require("rkallan-prettier-config"),
    semi: false,
};
```
