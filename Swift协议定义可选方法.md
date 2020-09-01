### Swift中定义可选方法

#### 第一种方法（首选）：

```swif
protocol MyProtocol {
    func doSomething()
}

//必须额外定义一个extension来实现协议方法
extension MyProtocol {
    func doSomething() {
        /* return a default value or just leave empty */
    }
}

struct MyStruct: MyProtocol {
    /* no compile error */
}
```

#### 第二种方法（使用`@objc optional`)：

```swi
//通过`@objc`修饰的协议就只能用在class，而struct和enum都无法使用了
@objc protocol MyProtocol {
    @objc optional func doSomething()
}

class MyClass: NSObject, MyProtocol {
    /* no compile error */
}
```



