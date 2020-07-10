### OC工程引用Swift静态库引发的问题

虽然现在OC和Swift混编都已经很成熟，但是今天在处理混编的过程中碰到一个OC工程调用Swift静态库的编译错误，以此做个记录

当OC工程去引用一个Swift静态库的时候（不要问我为啥要做成Swift静态库，因为Swift库中引用了一个OC的静态库，所以不得不做成静态库），会报出很多错误，类似如下：

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1ggjprgai7lj30pc09pwi1.jpg)

提示swift的系统库都找不到，网络搜索一番，找到如下的解决方案

https://stackoverflow.com/questions/52536380/why-linker-link-static-libraries-with-errors-ios

就是创建一个空的swift文件，然后这时xcode会提示是否创建bridging header文件，点击创建，重新编译就能修改该错误 

不过为何是这样的解决的方案，现在还是一头雾水



