## （2）while 循环

while 语句是一种"前测试"型循环，其通用形式如下：

```c
while(test_expr)         //test_expr 为循环判断的条件表达式
    body_statement       //当 test_expr 为真时重复执行 body_statement 语句
```

与 do-while 不同，while 循环在第一次执行 body_statement 之前就会测试 test_expr 的值。如果初始条件为假（test_expr = 0），那么循环体一次都不会执行。

为了用转移指令实现这一语义，编译器通常采用"先判断、再进入循环体"的策略。具体来说，可以将 while 循环转换为一个带前置判断的 do-while 式结构，如下所示：

```
t=test_expr;             //计算初始循环条件
if(!t)                   //若初始条件为假（t=0）
    goto done;           //跳过循环体，直接转至结束点
do
    body_statement       //执行循环体
    while(test_expr);    //重新测试条件
done:                    //循环结构的结束点
```

进一步展开为纯 goto 语句的形式：

```
t=test_expr;             //计算初始循环条件
if(!t)                   //若为假
    goto done;           //跳过循环
loop:
    body_statement       //执行循环体
    t=test_expr;         //重新计算条件
    if(t)                //若仍为真
        goto loop;       //继续下一轮
done:                    //循环结束
```

这种转换确保了 while 循环"先判断、后执行"的语义，同时复用了 do-while 的结构。