### DFA&NFA

`DFA(确定的有穷自动机) `有且只有一条离开该状态，以该边为标号的边

`NFA(不确定的有穷自动机)`对其边上的标号没有任何限制，一个符号离开同一状态的多条边，并且空串已也可以作为标号

![image-20200703142657270](https://tva1.sinaimg.cn/large/007S8ZIlgy1ggdwo5rq9rj30cc05tq35.jpg)

![image-20200703142733430](https://tva1.sinaimg.cn/large/007S8ZIlgy1ggdwo8v9ngj30c205qaae.jpg)

NFA可以通过子集构造法生成和其等价的DFA

正则表达式可以生成NFA，所以正则表达式可以找到一个对应的DFA与其等价

