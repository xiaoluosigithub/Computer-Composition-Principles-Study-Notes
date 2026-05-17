## （3）for 循环

for 循环是一种语法更紧凑的循环形式，其通用形式如下：

```c
for(init_expr; test_expr; update_expr)
    body_statement       //body_statement 为循环体执行语句
```

init_expr 为初始化表达式，用于初始化循环计数器（如 i = 0）；test_expr 为条件判断表达式，每次执行循环体前测试（如 i < 10）；update_expr 为更新表达式，每次循环体执行完后执行（如 i++）。

从执行逻辑上看，for 循环完全等价于下面这段 while 循环代码：

```c
init_expr;               //初始化（只执行一次）
while(test_expr) {       //每次循环前判断条件
    body_statement       //执行循环体
    update_expr;         //更新循环变量
}
```

因此，可以先将 for 循环转换为 while 形式，再按照前述方法转换为 goto 语句：

```
init_expr;               //执行初始化
t=test_expr;             //测试初始条件
if(!t)                   //若初始条件为假
    goto done;           //跳过循环
loop:
    body_statement       //执行循环体
    update_expr;         //执行更新操作
    t=test_expr;         //重新测试条件
    if(t)                //若条件仍为真
        goto loop;       //跳回循环体
done:
```

下面以一个具体的 C 语言函数为例，展示 for 循环如何被转换为汇编代码：

```c
int nsum_for(int n) {
    int i;
    int result = 0;
    for(i=1; i<=n; i++)
        result += i;
    return result;
}
```

在这段代码中，for 循环的各个组成部分如下：

```
init_expr       i=1
test_expr       i<=n
update_expr     i++
body_statement  result += i
```

通过替换前面给出的模板中的相应位置，很容易将 for 循环转换为 while 或 do-while 循环。将这个函数翻译为 goto 语句代码后，不难得出其过程体的汇编代码：

```asm
mov  ecx, dword ptr [ebp+8]   #R[ecx]←M[R[ebp]+8]，即加载参数 n 到 ecx
mov  eax, 0                   #R[eax]←0，即初始化 result=0
mov  edx, 1                   #R[edx]←1，即初始化 i=1
cmp  edx, ecx                 #比较 i 与 n（R[edx] 与 R[ecx]）并设置标志位
jg   .L2                      #If greater，则转移到 L2
.L1:                          #循环体入口
add  eax, edx                 #R[eax]←R[eax]+R[edx]，即 result += i
add  edx, 1                   #R[edx]←R[edx]+1，即 i++
cmp  edx, ecx                 #再次比较 i:n
jle  .L1                      #If less or equal，则转移到 L1
.L2:                          #循环结束点
```

已知实参 n 已被压入调用函数的栈帧，其对应的存储地址为 R\[ebp]+8。编译器将频繁使用的局部变量优化到寄存器中：此处，result 被分配到 eax（同时也是返回值寄存器），i 被分配到 edx。由于 i 和 n 均为 int 型，判断条件 i≤n 属于有符号比较，因此使用 jle 和 jg 等有符号转移指令。
