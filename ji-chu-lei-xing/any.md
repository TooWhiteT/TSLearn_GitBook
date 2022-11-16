# Any

在编码阶段不能确定变量类型时指定any类型，来跳过编译检查, 可以赋任意值

```typescript
let a: any
a = 98 // 任意类型赋值
console.log(a.substring(1))  // 编译时会报错 number类型没有substring方法
a = "hello" // 最终赋值
console.log(a.substring(1)) 

// 存放任意类型的数组
let b: any[] = [1, "2", false] 
```
