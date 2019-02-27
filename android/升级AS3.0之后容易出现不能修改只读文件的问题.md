### Cannot set the value of read-only property 'outputFile' for ApkVariantOutputImpl_Decorated

#### 升级AS3.0之后很多根据不同情况打包的apk名字就会遇到这个情况,这个错误度娘一下会有很多解释，你要是查看几篇之后也能解决，由于搜索之后倍感效率低下，就在这里简单修改一下，争取一步到位。大部分的博客是这样写的把each改为all，原因outputFile 是可读的，本质上没错，但是没有一个具体的描述，原来的each怎么用呢，基本没有写的特别明白的，我自己的例子:

```
applicationVariants.all { variant ->  
        variant.outputs.all { output ->  
            def date = new Date()  
            def formattedDate = date.format('yyyyMMdd')  
            def fileName  
            if (variant.buildType.name == "release") {  
                // 输出apk名称为app_100_release.apk  
                fileName = "xxx_V${defaultConfig.versionName}.apk"  
            } else if (variant.buildType.name == "debug") {  
                // 输出apk名称为app_100_debug.apk  
                fileName = "xxx_debug_V${defaultConfig.versionName}_${formattedDate}.apk"  
            } else {  
                // 输出apk名称为app_v1.0.0_2017-12-11_101_beta.apk  
                fileName = "xxx_Beta_V${defaultConfig.versionName}.apk"  
            }  
            output.outputFile = new File(output.outputFile.parent, fileName)  
        }  
    }  

```

#### 改完后是：
```
android.applicationVariants.all { variant ->  
        variant.outputs.all {//这里是all，下面是根据自己的情况来定制  
            def date = new Date()  
            def formattedDate = date.format('yyyyMMdd')  
            def fileName  
            if (variant.buildType.name == "release") {  
                // 输出apk名称为app_100_release.apk  
                fileName = "xxx_V${defaultConfig.versionName}.apk"  
            } else if (variant.buildType.name == "debug") {  
                // 输出apk名称为app_100_debug.apk  
                fileName = "xxx_debug_V${defaultConfig.versionName}_${formattedDate}.apk"  
            } else {  
                // 输出apk名称为app_v1.0.0_2017-12-11_101_beta.apk  
                fileName = "xxx_Beta_V${defaultConfig.versionName}.apk"  
            }  
            //outputFileName = "HuaxiaSign_${defaultConfig.versionName}_${formattedDate}.apk"  
            //很多博客只是写了上面这句话，没有具体赋值，自己来选择赋值给outputFileName  
            outputFileName = fileName  
        }  
    } 
    
```

##### 改完保存重新run一下就ok

Copyright (c) 2018-02-08, lhr