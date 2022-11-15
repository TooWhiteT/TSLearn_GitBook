# 元组 Tuple

元组类型允许表示一个已知元素数量和类型的数组，各元素的类型不必相同。

```typescript
let x: [string, number];
// 正确赋值
x = ['hello', 10];
// 错误赋值
x = [10, 'hello']; // 赋值类型与定义类型不一致
```

使用索引访问已知的元素，会得到正确的类型

```typescript
let a: string = x[0]; // string
let b: number =x[1]; // number
```

<mark style="color:blue;">**当访问一个越界的元素，会使用联合类型(Union Types)替代**</mark>

```typescript
let c: (string | number) = x[2]; // 会返回一个联合类型 使用声明过的类型组成一个联合类型
x[3] = "Test"; // 这样没问题 
x[4] = false; // 这样的报错 boolean不在(string | number)联合类型中
```
