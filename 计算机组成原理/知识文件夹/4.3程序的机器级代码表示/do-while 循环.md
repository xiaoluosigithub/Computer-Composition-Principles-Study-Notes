do-while 语句是一种"后测试"型循环，其通用形式如下：

```c
do
    body_statement       //body_statement 为循环体执行语句
while(test_expr);        //test_expr 为循环继续的条件表达式
```

这种结构可以直接翻译成如下所示的条件和 goto 语句组合：

```
loop:                    //循环入口标签
    body_statement       //执行循环体语句（首次进入时必然执行）
    t=test_expr;         //计算循环条件
    if(t)                //若条件为真（t≠0）
        goto loop;       //跳回 loop 标签，继续下一轮迭代
```

由于循环体在条件判断之前执行，因此无论 test_expr 的初始值是什么，body_statement 至少会被执行一次。每次执行结束时，程序会重新计算 test_expr 的值；如果结果为真（非零），就跳回循环开头继续执行；否则，顺序执行后续代码，退出循环。

![[Pasted image 20260516161803.png]]