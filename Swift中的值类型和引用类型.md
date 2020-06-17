### Swift中的值类型和引用类型

* Swift中的`struct`,`enum`,`tuple`都是**值类型**，**赋值使用深拷贝，即每个实例保持一份数据拷贝**，而平常经常使用的`Float`,`Int`,`Double`,`String`,`Array`,`Dictionary`,`Set`都是基于结构体实现的，所以它们也是值类型，可以说Swift中`struct`占据了半壁江山

* `class`和`closure`（闭包）是**引用类型**，对内存的管理沿用`ARC`那一套，**赋值是采用浅拷贝，即所有实例共享一份数据拷贝**

  

**值类型**（`withUnsafePointer(to:_:)` 函数可以用来打印值类型变量的内存地址）

```swift
struct PersonStruct {
    var name = "name"
    var age = 20
}

var personStructA = PersonStruct()
var personStructB = personStructA
withUnsafePointer(to: &personStructA) { print("\($0)") } //0x00000001058cdc60
withUnsafePointer(to: &personStructB) { print("\($0)") } //0x00000001058cdc78
//可以看出两者的地址不一致

print(personStructA.name,personStructA.age) //name 20
print(personStructB.name,personStructB.age) //name 20

personStructB.name = "nameB"
personStructB.age = 30

print(personStructA.name,personStructA.age) //name 20
print(personStructB.name,personStructB.age) //nameB 30
```



**引用类型**（`print(Unmanaged.passUnretained(T).toOpaque())`函数打印引用类型内存地址）

```swift
class PersonClass {
    var name = "name"
    var age = 20
}

var personClassA = PersonClass()
var personClassB = personClassA
print(Unmanaged.passUnretained(personClassA).toOpaque()) //0x0000600002b12bb0
print(Unmanaged.passUnretained(personClassB).toOpaque()) //0x0000600002b12bb0
//可以看出两者的地址是一样的

print(personClassA.name,personClassA.age) //name 20
print(personClassB.name,personClassB.age) //name 20

personClassB.name = "nameB"
personClassB.age = 30

//由于是同一份数据，所以打印出的结果是一样的
print(personClassA.name,personClassA.age) //nameB 30
print(personClassB.name,personClassB.age) //nameB 30
```

