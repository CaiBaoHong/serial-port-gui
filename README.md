# serial-port-gui

## Project setup
```bash
yarn
```

### Start electron application

```bash
yarn electron:serve
```

remember to config this in `vue.config.js`:

```javascript
module.exports = {
  pluginOptions: {
    electronBuilder: {
      externals: ['serialport']
    }
  }
}
```

### Reproduct the issue

```bash
$ yarn
yarn install v1.19.1
[1/4] Resolving packages...
[2/4] Fetching packages...
info fsevents@1.2.9: The platform "linux" is incompatible with this module.
info "fsevents@1.2.9" is an optional dependency and failed compatibility check. Excluding it from installation.
info fsevents@2.1.1: The platform "linux" is incompatible with this module.
info "fsevents@2.1.1" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
warning " > less-loader@5.0.0" has unmet peer dependency "webpack@^2.0.0 || ^3.0.0 || ^4.0.0".
[4/4] Building fresh packages...
$ electron-builder install-app-deps
  • electron-builder  version=21.2.0
  • rebuilding native dependencies  dependencies=@serialport/bindings@2.0.8 platform=linux arch=x64
  • install prebuilt binary  name=@serialport/bindings version=2.0.8 platform=linux arch=x64
  • build native dependency from sources  name=@serialport/bindings
                                          version=2.0.8
                                          platform=linux
                                          arch=x64
                                          reason=prebuild-install failed with error (run with env DEBUG=electron-builder to get more information)
                                          error=prebuild-install info begin Prebuild-install version 5.3.2
    prebuild-install info looking for cached prebuild @ /home/caibh/.npm/_prebuilds/62a8e4-bindings-v2.0.8-electron-v73-linux-x64.tar.gz
    prebuild-install http request GET https://github.com/node-serialport/node-serialport/releases/download/v2.0.8/bindings-v2.0.8-electron-v73-linux-x64.tar.gz
    prebuild-install http 404 https://github.com/node-serialport/node-serialport/releases/download/v2.0.8/bindings-v2.0.8-electron-v73-linux-x64.tar.gz
    prebuild-install WARN install No prebuilt binaries found (target=6.1.1 runtime=electron arch=x64 libc= platform=linux)
    
  • rebuilding native dependency  name=@serialport/bindings version=2.0.8
Done in 35.12s.
```


