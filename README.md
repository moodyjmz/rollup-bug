# \<rollup-bug>

Demo to show bug in repo. So far, only reproducible on mac (10.14.16, node 13.6.0).

This is just for convenience and is simply the default open-wc init.

Downgrading the installed `@rollup/pluginutils` to 3.0.10 removes the issue.

```bash
[es-dev-server] internal/modules/cjs/loader.js:628
[es-dev-server]   throw e;
[es-dev-server]   ^
[es-dev-server] 
[es-dev-server] Error: No valid exports main found for '~/rollup-bug/node_modules/@rollup/pluginutils'
[es-dev-server]     at resolveExportsTarget (internal/modules/cjs/loader.js:625:9)
[es-dev-server]     at applyExports (internal/modules/cjs/loader.js:502:14)
[es-dev-server]     at resolveExports (internal/modules/cjs/loader.js:551:12)
[es-dev-server]     at Function.Module._findPath (internal/modules/cjs/loader.js:657:22)
[es-dev-server]     at Function.Module._resolveFilename (internal/modules/cjs/loader.js:960:27)
[es-dev-server]     at Function.Module._load (internal/modules/cjs/loader.js:855:27)
[es-dev-server]     at Module.require (internal/modules/cjs/loader.js:1033:19)
[es-dev-server]     at require (internal/modules/cjs/helpers.js:72:18)
[es-dev-server]     at Object.<anonymous> (~/rollup-bug/node_modules/@rollup/plugin-node-resolve/dist/index.js:11:19)
[es-dev-server]     at Module._compile (internal/modules/cjs/loader.js:1144:30) {
[es-dev-server]   code: 'MODULE_NOT_FOUND'
[es-dev-server] }
[es-dev-server] es-dev-server --app-index demo/index.html --node-resolve --open --watch exited with code 1
--> Sending SIGTERM to other processes..
[tsc] npm run tsc:watch exited with code SIGTERM

```

## Installation
```bash
npm i
```

## Local Demo with `es-dev-server`
```bash
npm start
```
To run a local development server that serves the basic demo located in `demo/index.html`.

This will run on Windows and fail on Mac.
