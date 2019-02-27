## vue中webpack打包sass之后-webkit-line-clamp不生效的一个坑
```
vue项目中用webpack打包sass发现-webkit-line-clamp熟悉不生效，特别是ios，查遍文档之后发现是因为-webkit-box-orient: vertical;这个属性在打包过程中被自动注释掉了
```

#### 解决办法是如下
```
  /*! autoprefixer: off */
  -webkit-box-orient: vertical;
  /* autoprefixer: on */
```
#### 在-webkit-box-orient: vertical;前后各加上一句注释得以解决问题

#### 参考 https://github.com/postcss/autoprefixer/issues/776