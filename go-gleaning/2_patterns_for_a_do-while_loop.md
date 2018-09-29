# 2 patterns for a do-while loop in Go

go语言没有类似C/Java中的do-while循环，可以通过for循环模拟

```java
do {
    work();
} while (condition);
```

#### 1.

```go
for ok := true; ok; ok = condition {
    work()
}
```

#### 2.

```go
for {
    work()
    if !condition {
        break
    }
}
```

源: [https://yourbasic.org/golang/do-while-loop/](https://yourbasic.org/golang/do-while-loop/)