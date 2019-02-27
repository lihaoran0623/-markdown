## npm install 错误 安装 chromedriver 失败的解决办法



#####  npm 安装 chromedriver 时，偶尔会出错，错误提示类似于：

```
> chromedriver@2.27.2 install /Users/Mario/Work/Lab/waylens-all-in-one-site/node_modules/chromedriver
> node install.js

Downloading https://chromedriver.storage.googleapis.com/2.27/chromedriver_mac64.zip
Saving to /var/folders/7l/mhhqzhps0y59by7pf04nyx5r0000gn/T/chromedriver/chromedriver_mac64.zip
events.js:161
throw er; // Unhandled 'error' event
^

Error: connect ETIMEDOUT 74.125.23.128:443
at Object.exports._errnoException (util.js:1023:11)
at exports._exceptionWithHostPort (util.js:1046:20)
at TCPConnectWrap.afterConnect [as oncomplete] (net.js:1090:14)
```
###### 经分析发现，某些版本下，chromedriver 的 zip 文件 url 的响应是 302 跳转，而在 install.js 里使用的是 Node.js 内置的 http 对象的 get 方法无法处理 302 跳转的情况；而在另外一些情况下，则是因为 googleapis.com 被墙了，此时即使采用科学上网的方法也仍然无法获取文件。

###### 无论是上述哪种情况，可以使用下面的命令安装：

```
npm install chromedriver --chromedriver_cdnurl=http://cdn.npm.taobao.org/dist/chromedriver
```

###### 使用 cnpm 安装亦可。

Copyright (c) 2018-02-02, lhr
