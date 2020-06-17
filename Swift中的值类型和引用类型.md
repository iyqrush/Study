### Swift中的值类型和引用类型

* Swift中的`struct`,`enum`,`tuple`都是**值类型**，**赋值使用深拷贝，即每个实例保持一份数据拷贝**，而平常经常使用的`Float`,`Int`,`Double`,`String`,`Array`,`Dictionary`,`Set`都是基于结构体实现的，所以它们也是值类型，可以说Swift中`struct`占据了半壁江山
* `class`和`closure`（闭包）是**引用类型**，对内存的管理沿用`ARC`那一套，**赋值是采用浅拷贝，即所有实例共享一份数据拷贝**

