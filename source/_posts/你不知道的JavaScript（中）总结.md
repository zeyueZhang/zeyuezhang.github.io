# 你不知道的JavaScript（中）总结

## 类型

### 内置类型

七种内置类型
- 空值（null）
- 未定义（undefined）
- 布尔值（ boolean）
- 数字（number）
- 字符串（string）
- 对象（object）
- 符号（symbol，ES6 中新增）
<!--more-->
除对象外，其他被称为基本类型
可使用typeof进行基本类型的检验，但是**null**除外
```javascript
  typeof null === "object"; // true
```
这是一个bug，历史由来已久，若想检测 **null** 的值，需复合条件来检测
```javascript
  const a = null
  (!a && typeof a === "object") // true
```

还有一种情况，可能会疑惑 
```javascript
  typeof functiong a(b, c){...} ===  function //true
```
**function** 是 **object** 的一个子类型，不仅是对象，也可以拥有属性
函数对象的 **length** 属性是其拥有参数的个数
```javascript
  a.length // 2
```
同样数组也是对象的子类型
```javascript
  typeof [1,2,3] === "object" //true
```

### 值和类型

js中的变量是没有类型的，只有值才有。typeof检测的是变量的值的类型
```javascript
  const a = '22'
  typeof a // 'string' 检测的是a变量的值'22'的类型
```
typeof 运算符总是返回一个字符串
```javascript
  const a = 22
  typeof typeof a  // string
```