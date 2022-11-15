---
description: TypeScript支持与JavaScript几乎相同的数据类型，并在其基础上进行了扩展
---

# 基础类型

### 常见类型

* 布尔值 boolean
* 数字 number
* 字符串 string
* 数组 Array
* 元组 Tuple
* 枚举 enum
* Any
* Void
* Symbol
* Null 和 Undefined
* Never
* Object

### 类型使用

#### 布尔值

{% code lineNumbers="true" %}
```typescript
let T: boolean = true;
let F: boolean = false;
```
{% endcode %}

#### 数字

```typescript
let decNum: number = 6; // 十进制
let hexNum: number = 0xf00d; // 十六进制
let binNum: number = 0b1010; // 二进制
let octNum: number = 0o744; // 八进制
```

和JavaScript一样，<mark style="color:red;">**TypeScript里的所有数字都是浮点数**</mark>。 这些浮点数的类型是 number。 除了支持十进制和十六进制字面量，TypeScript还支持ECMAScript 2015中引入的二进制和八进制字面量。

#### 字符串

<pre class="language-typescript"><code class="lang-typescript"><strong>// 使用双引号"" or 单引号'' 表示字符串
</strong><strong>let name: string = "Tom";
</strong>let sex: string = '男';
// 字符串模板 
// 使用``反引号包裹字符串 并加入 ${ expr } 这种形式嵌入表达式
let name: string = `Gene`;
let age: number = 37;
let sentence: string = `Hello, my name is ${ name }.

I'll be ${ age + 1 } years old next month.`;</code></pre>

#### 数组

数组声明方式一

```typescript
let arr: number[] = [1, 2, 3];
```

数组声明方式二

```typescript
let arr: Array<number> = [1, 2, 3];
```

#### 元组

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

#### 枚举 enum

enum类型是对JavaScript标准数据类型的一个补充

```typescript
enum Color {Red, Green, Blue}
let color: Color = Color.Green; // 1
```

默认情况下，从0开始为元素编号。 你也可以手动的指定成员的数值。

```typescript
enum Color {Red = 1, Green, Blue}
let color: Color = Color.Green; // 2
```

全部手动赋值

```typescript
enum Color {Red = 128, Green = 255, Blue = 90}
let color: Color = Color.Green; // 255
```

枚举类型提供的一个快捷方式，你可以通过枚举的值得到它的枚举名字。

```typescript
enum Color {Red = 1, Green, Blue}
let colorName: string = Color[2];// Green
```

#### Any



### 类型转换

