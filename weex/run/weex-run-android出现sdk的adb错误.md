## weex run android时报错:Environment variable $ANDROID_HOME not found !



#####  错误提示类似于：

```
17:53:18 : npm run build

> weex-test@1.0.0 build /Volumes/code/weex-test
> webpack --env.NODE_ENV=common

Hash: 5655ea6c6d37f4fc2bdf793d9e5d1f74d4ddb942
Version: webpack 3.10.0
Child
    Hash: 5655ea6c6d37f4fc2bdf
    Time: 5397ms
           Asset    Size  Chunks                    Chunk Names
    index.web.js  644 kB       0  [emitted]  [big]  index
       [0] (webpack)/buildin/global.js 509 bytes {0} [built]
       [5] ./.temp?entry=true 792 bytes {0} [built]
      [10] ./src/index.vue 1.52 kB {0} [built]
      [11] ./node_modules/_babel-loader@6.4.1@babel-loader/lib!./node_modules/_vue-loader@12.2.2@vue-loader/lib/selector.js?type=script&index=0!./src/index.vue 660 bytes {0} [built]
      [32] ./node_modules/_vue-loader@12.2.2@vue-loader/lib/template-compiler?{"id":"data-v-07213dd8","hasScoped":false}!./node_modules/_vue-loader@12.2.2@vue-loader/lib/selector.js?type=template&index=0!./src/index.vue 866 bytes {0} [built]
        + 28 hidden modules
Child
    Hash: 793d9e5d1f74d4ddb942
    Time: 5029ms
       Asset     Size  Chunks             Chunk Names
    index.js  23.2 kB       0  [emitted]  index
       [0] ./src/index.vue?entry=true 1.55 kB {0} [built]
       [1] ./node_modules/_weex-vue-loader@0.5.15@weex-vue-loader/lib/script-loader.js!./node_modules/_babel-loader@6.4.1@babel-loader/lib!./node_modules/_weex-vue-loader@0.5.15@weex-vue-loader/lib/selector.js?type=script&index=0!./src/index.vue 660 bytes {0} [built]
      [18] ./node_modules/_weex-vue-loader@0.5.15@weex-vue-loader/lib/template-compiler.js?id=data-v-2964abc9!./node_modules/_weex-vue-loader@0.5.15@weex-vue-loader/lib/selector.js?type=template&index=0!./src/index.vue 499 bytes {0} [built]
        + 16 hidden modules
17:53:24 : Move JSbundle to dist'
17:53:24 : Copied to /Volumes/code/weex-test/platforms/android/app/src/main/assets/dist/index.js
17:53:24 : Move 1 files.
17:53:24 : start Android app

17:53:24 : Environment variable $ANDROID_HOME not found !
You should set ANDROID_HOME in your environment first.
See https://spring.io/guides/gs/android/
/bin/sh: adb: command not found
/bin/sh: adb: command not found
```
###### 遇到这个情况需要设置一下 Android SDK目录platform-tools中的adb。


```
vi ~/.bash_profile
# step.2
ANDROID_HOME={你SDK的目录地址，比如/Users/Android/sdk}
export ANDROID_HOME
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/platform-tools
# step.3 保存 ~/.bash_profile 文件中的修改
# step.4 验证，adb是否起作用，如果不起作用就执行如下命令
source ~/.bash_profile
```

###### 如果你是在不知道你的sdk目录你可以下载一个android  studio ，进入设置里面搜索sdk即可

Copyright (c) 2018-02-02, lhr
