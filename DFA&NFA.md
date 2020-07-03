### DFA&NFA

`DFA(确定的有穷自动机) `有且只有一条离开该状态，以该边为标号的边

`NFA(不确定的有穷自动机)`对其边上的标号没有任何限制，一个符号离开同一状态的多条边，并且空串已也可以作为标号

![image-20200703142657270](/Users/zhengzhilin/Library/Application Support/typora-user-images/image-20200703142657270.png)

![image-20200703142733430](/Users/zhengzhilin/Library/Application Support/typora-user-images/image-20200703142733430.png)

NFA可以通过子集构造法生成和其等价的DFA

正则表达式可以生成NFA，所以正则表达式可以找到一个对应的DFA与其等价

