##`str.format`函数是python的一种格式化字符串函数，当然比`%`形式的功能更加完善。
1 **语法**
```
format(...)
    S.format(*args, **kwargs) -> string
    
    Return a formatted version of S, using substitutions from args and kwargs.
    The substitutions are identified by braces ('{' and '}'
```



`str.format`是通过`｛｝`和`：`来替代`%`

2 **位置表示**
```
'{0},{1}'.format('Mark','100')
Out[15]: 'Mark,100'
'{0},{1},{0}'.format('Mark','100')
Out[16]: 'mark,100,Mark'
```

3 **KEY的索引**
```
'{name} is {age} years old'.format(age = 20, name = 'Mark')
Out[20]: 'Mark is 20 years old'
```

4 **对象属性**
```
class name_age:
    def __init__(self, name, age):
        self.name, self.age = name, age
        def __str__(self):
            return "{self.name} is {self.age} old".format(self = self)

str(name_age('Mark', 20))
Out[23]:"Mark is 20 old"
```

5 **下标的索引**
```
"{0[0]}, {0[2]}".format(m)
Out[45]: 'Mark, 20'
```

`:`的作用是限定字符（串）格式的
6 **填充与对齐**
`^`，`>`，`<`，分别表示居中、右对齐、左对齐。
```
"{:>10}".format('111')
Out[54]: '       111'

"{:^10}".format('111')
Out[55]: '   111    '

"{:<10}".format('111')
Out[56]: '111       '

"{:m>10}".format('111')
Out[57]: 'mmmmmmm111'

"{:m<10}".format('111')
Out[58]: '111mmmmmmm'

"{:m^10}".format('111')
Out[59]: 'mmm111mmmm'

"{:*^10}".format('111')
Out[60]: '***111****'
```
另外`=`也是限定符，不过只对数值类型有用
```
"{:=10}".format('111')
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-65-7f69ac0a7ea5> in <module>()
----> 1 "{:=10}".format('111')

ValueError: '=' alignment not allowed in string format specifier

"{:=10}".format(111)
Out[66]: '       111'
```
7 **精度与浮点**
```
'{:.2f}'.format(1.11111)
Out[67]: '1.11'
```
8 [**官方文档**](https://www.python.org/dev/peps/pep-3101/)






























