

### 1. 三段式（Three-component loop）
这个和C/Java中格式一致

```go
sum := 0
for i := 1; i < 5; i++ {
    sum += i
}
fmt.Println(sum) // 10 (1+2+3+4)
```
>
1. The init statement, i := 1, runs.
2. The condition, i < 5, is computed.
	* If true, the loop body runs,
	* otherwise the loop is done.
3. The post statement, i++, runs.
4. Back to step 2.

另： i的作用域限制在循环内

### 2. while循环 (While loop)

省略掉前面的init语句和后面的操作语句，则得到一个while循环

```go
n := 1
for n < 5 {
    n *= 2
}
fmt.Println(n) // 8 (1*2*2*2)
```

1. The condition, n < 5, is computed.
	* If true, the loop body runs,
	* otherwise the loop is done.
2. Back to step 1.

### 3. 无限循环（Infinite loop）

在上面的基础上如果省略中间的条件语句，则得到一个无限循环：

```go
sum := 0
for {
    sum++ // repeated forever
}
fmt.Println(sum) // never reached
```


### 4. For-each range loop

使用range loop循环访问<i>slices, arrays, maps, channels or strings</i>中的元素是一个比较好的方式

```go
strings := []string{"hello", "world"}
for i, s := range strings {
    fmt.Println(i, s)
}
```

```go
0 hello
1 world
```

参见[Range loops (for-each loops)](https://yourbasic.org/golang/for-loop-range-array-slice-map-channel/)进一步获取详情.


#### 5. 退出循环（Exit loop）

**break**和**continue**关键字的工作方式同C/Java一致.

```go
sum := 0
for i := 1; i < 5; i++ {
    if i%2 != 0 { // skip odd numbers
        continue
    }
    sum += i
}
fmt.Println(sum) // 6 (2+4)
```

- A **continue** statement begins the next iteration of the innermost **for** loop at its post statement (i++).
- A **break** statement leaves the innermost **for**, [**switch**](https://yourbasic.org/golang/switch-statement/) or [**select**](https://yourbasic.org/golang/select-explained/) statement.

源: [5 basic for loop patterns](https://yourbasic.org/golang/for-loop/)