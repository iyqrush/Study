### typealias 类型别名

**typealias 是用来为已经存在的类型重新定义名字的，通过命名，可以使代码变得更加清晰。**

### associatedtype 关联类型

**关联类型为协议中的某个类型提供了一个占位名（或者说别名），其代表的实际类型在协议被采纳时才会被指定。说白了，`associatedtype`为`protocol`提供了泛型的能力**

**swift的协议是采用`associatedtype`来实现泛型的**

```swift
//不支持如下定义
protocol GeneratorType {
    public mutating func next() -> Element?
}
//采用associatedtype来声明一个类型的类型的占位符作为协议定义的一部分，来达到泛型的效果
protocol GeneratorType {
    associatedtype Element
    public mutating func next() -> Self.Element?
}
```