# Closure(学习Javascript闭包（Closure）)

闭包（closure）是Javascript语言的一个难点，也是它的特色，很多高级应用都要依靠闭包实现。

下面就是我的学习笔记，对于Javascript初学者应该是很有用的。

### 一、变量的作用域

要理解闭包，首先必须理解Javascript特殊的变量作用域。

变量的作用域无非就是两种：全局变量和局部变量。

Javascript语言的特殊之处，就在于函数内部可以直接读取全局变量。
```JS
var n=999;
　　function f1(){
　　　　alert(n);
　　}

　　f1(); // 999
```
## 另一方面，在函数外部自然无法读取函数内的局部变量。
```JS
function f1(){
　　　　var n=999;
　　}

　　alert(n); // error
```

## 这里有一个地方需要注意，函数内部声明变量的时候，一定要使用var命令。如果不用的话，你实际上声明了一个全局变量！

```html
function f1(){
　　　　n=999;
　　}

　　f1();

　　alert(n); // 999
```

## 刷新调用refresh

```html
this.$refs.upload.refresh();
```

### Api

成员    |    说明 |       类型              |    默认值
------- | --------| ---------------------|------------
upload-button|上传按钮	|String|--
url    | 文件上传地址 | String | --
form-data | 上传需要携带的附加参数	 |Object     | null
accept  | 上传指定的类型     |  Object           | null
key-generator  | 设置key参数|function|function (file) { const currentTime = new Date().getTime();const key = currentTime + "." + file.name;return key;}
progress  | 正在上传中回调方法	     |           function           | --
success   | 上传成功回调方法	     |           function           | --
before| 上传前回调方法	|function|--
error|上传失败回调方法	|function|--
complete|上传完成回调方法，不管成功或者失败|function|--
multiple|是否支持多文件上传|Boolean|false
refresh|刷新调用|function|--
