# Personal config files

I use this config in all my projects. No need to copy/paste anymore 😄

## Supported tools

- [x] Prettier
- [x] Biome
- [ ] ESLint
- [x] Typescript

## Install

```sh
npm i -D @decampsrenan/config
```

## Usage

### Prettier

```json5
// package.json
{
  "name": "...",
  "prettier": "@decampsrenan/config/prettier-default"
  // Use "prettier-astro" to format astro files
  // "prettier": "@decampsrenan/config/prettier-astro"
}
```

Or if you need more control on the settings:

```js
// .prettierrc.mjs
import config from "@decampsrenan/config/prettier-default"

export default {
  ...config
  // Override with your custom needs here
}
```

Then run the following commands to check or update files if needed:

```sh
npx prettier -c ./ # Check if there is some files to update
npx prettier -w ./ # Update files
```

### Biome

Biome requires a `biome.json` file (no `package.json` support):

```json5
// biome.json
{
  "$schema": "https://biomejs.dev/schemas/2.4.7/schema.json",
  "extends": ["@decampsrenan/config/biome"]
}
```

Then run:

```sh
npx @biomejs/biome check ./ # Check formatting and linting
npx @biomejs/biome check --write ./ # Auto-fix
```

### TSConfig

```json5
// tsconfig.json
{
  "extends": "@decampsrenan/config/tsconfig"
  // Override with your custom needs here
}
```
