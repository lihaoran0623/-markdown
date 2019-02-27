### The "NPM run uat" command is executed to render the vendor error in the node-sass module.

#### The error is shown below.

```
ERROR in ./~/extract-text-webpack-plugin/loader.js?{"omit":1,"remove":true,"publicPath":"../../../"}!./~/vue-style-loader!./~/css-loader?{"minimize":false,"sourceMap":false}!./~/vue-loader/lib/style-compiler?{"id":"data-v-cc45a214","scoped":false,"hasInlineConfig":false}!./~/sass-loader/lib/loader.js?{"sourceMap":false}!./~/vue-loader/lib/selector.js?type=styles&index=0!./src/pages/stock/stock-index/App.vue
Module build failed: ModuleBuildError: Module build failed: Error: ENOENT: no such file or directory, scandir '/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/vendor'
    at Object.fs.readdirSync (fs.js:924:18)
    at Object.getInstalledBinaries (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/lib/extensions.js:128:13)
    at foundBinariesList (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/lib/errors.js:20:15)
    at foundBinaries (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/lib/errors.js:15:5)
    at Object.module.exports.missingBinary (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/lib/errors.js:45:5)
    at module.exports (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/lib/binding.js:15:30)
    at Object.<anonymous> (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/node-sass/lib/index.js:14:35)
    at Module._compile (module.js:660:30)
    at Object.Module._extensions..js (module.js:671:10)
    at Module.load (module.js:573:32)
    at tryModuleLoad (module.js:513:12)
    at Function.Module._load (module.js:505:3)
    at Module.require (module.js:604:17)
    at require (internal/module.js:11:18)
    at Object.<anonymous> (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/sass-loader/lib/loader.js:3:14)
    at Module._compile (module.js:660:30)
    at runLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/webpack/lib/NormalModule.js:192:19)
    at /Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:364:11
    at /Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:170:18
    at loadLoader (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/loadLoader.js:27:11)
    at iteratePitchingLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:169:2)
    at iteratePitchingLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:165:10)
    at /Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:173:18
    at loadLoader (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/loadLoader.js:36:3)
    at iteratePitchingLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:169:2)
    at iteratePitchingLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:165:10)
    at /Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:173:18
    at loadLoader (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/loadLoader.js:36:3)
    at iteratePitchingLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:169:2)
    at runLoaders (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/loader-runner/lib/LoaderRunner.js:362:2)
    at NormalModule.doBuild (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/webpack/lib/NormalModule.js:179:3)
    at NormalModule.build (/Volumes/code/nodetest/HKAPP_PACKAGE/node_modules/webpack/lib/NormalModule.js:268:15)
```

#### Reference solution

##### Rerun the installation of the "node-sass" module.

```
sudo cnpm install node-sass
```

Copyright (c) 2018-02-02, lhr