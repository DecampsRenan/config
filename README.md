# Personal config files

I use this config in all my projects. No need to copy/paste anymore 😄

## Supported tools

- [x] Prettier
- [x] Biome (replaces ESLint + Prettier)
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

[Biome](https://biomejs.dev/) is a fast formatter and linter that can replace both Prettier and ESLint.

```json5
// biome.json
{
  "extends": ["@decampsrenan/config/biome"]
  // Override with your custom needs here
}
```

Or if you need more control on the settings:

```json5
// biome.json
{
  "extends": ["@decampsrenan/config/biome"],
  "linter": {
    "rules": {
      "suspicious": {
        "noConsoleLog": "off" // Example: disable console.log warnings
      }
    }
  }
}
```

Then run the following commands:

```sh
npx @biomejs/biome check ./        # Check formatting and linting
npx @biomejs/biome check --write ./  # Fix issues automatically
npx @biomejs/biome lint ./         # Lint only
npx @biomejs/biome format ./       # Format only
```

### TSConfig

```json5
// tsconfig.json
{
  "extends": "@decampsrenan/config/tsconfig"
  // Override with your custom needs here
}
```
