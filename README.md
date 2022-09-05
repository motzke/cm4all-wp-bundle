# Development

- ensure you have NodeJS > v16.13 installed (example using nvm: `nvm install v16.13`). 

- enable corepack : `corepack enable`

- install dependencies : `corepack pnpm install`

## debugging

debugging can be done using `ndb` wrapped in the package.json `debug` script: 

Examples: 

```
// debug the code runned during package.json "test" script
corepack pnpm run debug test

// debug the code runned during package.json "start" script
corepack pnpm run debug start
```

# Usage

## CLI

## JS API

- `bundle(options)`

### Options

- `boolean` `verbose` (optional, default=`false`): enabling verbose mode results in more output,
- `string}` `mode` (optional, default=`production`): possible values are `development` and `production`
- `[string]` `entryPoints`: array of entry points. At least one entry point is required. An entry point is a path to a file transpiled by esbuild.
- `string` `outdir`: target directory,
- `object<string,string>` `expose` (optional): object with entry points as keys, and global name for the generated js content as value. Example: Exposing entrypoint `foo.js` to global name `my.foo` will result in `window.my.foo = <exports of foo.js>`.
- `string` `banner` (optional): banner to be added to the generated content.
- `string` `footer` (optional): footer to be added to the generated content.
- `boolean` `watch` (optional): if true the bundle will be rebuilt when source files change
- `object` `sass` (optional): options for sass/scss plugin (see https://sass-lang.com/documentation/js-api/interfaces/Options)
