# Farmbot Build Environment
There are a number of things that can (and should) be configured at compile time
via shell environment variables.

## Firmware Signing
We produce signed releases in PROD environment. export `PRIV_KEY_FILE` to be the private key file.

## IO debugger
If you want more verbose logs you can export `DEBUG_LOG`. This will cause (a lot of) messages
to be displayed on the current tty.

## Mix Environment
You can set `MIX_ENV=prod` or `MIX_ENV=dev` (default) to change the environment
of the farmbot application.

## Mix Target
When building firmware you can set the target.
`MIX_TARGET=rpi2`

## Webpack
Farmbot's `Configurator` application uses Webpack to compile a TypeScript Project
into a static website that gets served by `Plug`.

Webpack is configured via a package called `ex_webpack`. Default behavior is to
watch the web source files for changes and recompile. This adds extra time to the
initial compile of the application and can be just generally annoying. To disable
this export `USE_WEBPACK=false`

## Configurator
The Configurator app is started by default on port `5000`.
This can be changed by exporting in development mode only:
```bash
CONFIGURATOR_PORT=4000
```

## Redis Server
In development mode you can export
```bash
REDIS_SERVER=true
REDIS_SERVER_PORT=6379
```
