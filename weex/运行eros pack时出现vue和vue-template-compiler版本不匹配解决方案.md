## 运行eros pack时出现vue和vue-template-compiler版本不匹配解决方案

### 命令行错误代码如下：

~~~
ERROR in ./src/js/pages/home/index/invoiceDetail/invoiceDetail.vue?entry=true
Module build failed: Error:

Vue packages version mismatch:

- vue@2.5.13
- vue-template-compiler@2.5.16

This may cause things to work incorrectly. Make sure to use the same version for both.
If you are using vue-loader@>=10.0, simply update vue-template-compiler.
If you are using vue-loader@<10.0 or vueify, re-installing vue-loader/vueify should bump vue-template-compiler to the latest.

    at Object.<anonymous> (/usr/local/lib/node_modules/eros-cli/node_modules/vue-template-compiler/index.js:8:9)
    at Module._compile (module.js:660:30)
    at Object.Module._extensions..js (module.js:671:10)
    at Module.load (module.js:573:32)
    at tryModuleLoad (module.js:513:12)
    at Function.Module._load (module.js:505:3)
    at Module.require (module.js:604:17)
    at require (internal/module.js:11:18)
    at Object.<anonymous> (/usr/local/lib/node_modules/eros-cli/node_modules/weex-vue-loader/lib/parser.js:2:16)
    at Module._compile (module.js:660:30)
~~~

### 通常情况是由于将vue安装在了根目录造成的
### 使用以下命令修复下

> weex xbind repair toolkit-repair

> weex repair

<center>&copy;2018 cn1994</center>