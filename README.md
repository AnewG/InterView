# InterView

## 字符串替换

```
Q: 将字符串中所有x替换成yy。

A: 从内存角度考虑。
   1.若从左往右遍历，循环进行"匹配-位后移-插入"操作，会有字符被移动多次才移动到最终确定位置。
   2.另一种方式为先遍历一遍，算出替换后的总长度，然后从右往左开始遍历，
     一旦匹配直接往最后空余空间移动，所有字符最多只会被移动一次，时间n。
     
Tips: 对重复部分进行优化提高效率。例如斐波那契串生成函数的优化，里面有不少函数重复计算。
```

```
Tips: 对于问题多注意：1.完整性(边界检查)。2.鲁棒性(防御式编程处理错误输入)。
```

## 求字符串排列

```
Q: 输入字符串abc，打印出a,b,c能排列出的所有字符串

A: 分解问题，递归处理。
每次递归将字符串分为前面第一个字符与剩余的字符串（本例：a,bc b,ac c,ab），递归到最后2位时（2种排列）开始返回并乘与各自分解的个数。
d,a,m,n 
  => d, amn
    => a, mn
    => m, an
    => n, am
  => a, dmn
    ...
  => m, dan
    ...
  => n, dam
    ...
会发现规律是阶乘
像判断有没可能的问题和有多少种符合条件之类的问题都可以用类似解法
```

## 列出所有子数组

```
function SubArray(arr) {
    var n = arr.length;
    var temp = [];
    for (var i = 0; i < n; i++) {
        for (var j = i; j < n; j++) {
            for (var k = i; k <= j; k++) {
                temp.push(arr[k]);
            }
	    console.log(temp);
	    temp = [];
        }
    }
}
```

## 逆序对相关

```
逆序对一般都与排序有关，比如统计逆序对个数其实就是统计分治排序的交换次数
```
