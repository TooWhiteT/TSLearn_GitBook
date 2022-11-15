# 枚举 enum

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
