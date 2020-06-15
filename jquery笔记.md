# jquery笔记

#### **层级选择器**

- `jQuery`层级选择器----包含选择器、子选择器、相邻选择器、兄弟选择器4种
- a.包含选择器：`$("a b")`在给定的祖先元素下匹配所有后代元素。(不受层级限制)
- b.子选择器：`$("parent > child")`在给定的父元素下匹配所有子元素。
- c.相邻选择器：`$("prev + next")` 匹配所有紧接在`prev`元素后的`next`元素。
- d.兄弟选择器：`$("prev ~ siblings")` 匹配prev元素之后的所有`sibling`元素。

###### jQuery 元素选择器

$("p") 选取 <p> 元素。

$("p.intro") 选取所有 class="intro" 的 <p> 元素。

$("p#demo") 选取所有 id="demo" 的 <p> 元素。

###### 过滤选择器

**一、基本过滤选择**

| 选择器       | 说明                           | 返回     |
| ------------ | ------------------------------ | -------- |
| `:first`     | 匹配找到的第1个元素            | 单个元素 |
| `:last`      | 匹配找到的最后一个元素         | 单个元素 |
| `:eq`        | 匹配一个给定索引值的元素       | 单个元素 |
| `:even`      | 匹配所有索引值为偶数的元素     | 集合元素 |
| `: odd`      | 匹配所有索引值为奇数的元素     | 集合元素 |
| `:gt(index)` | 匹配所有大于给定索引值的元素   | 集合元素 |
| `:lt(index)` | 匹配所有小于给定索引值的元素   | 集合元素 |
| `:not`       | 去除所有与给定选择器匹配的元素 | 集合元素 |
| `:animated`  | 选取当前正在执行动画的所有元素 | 集合元素 |
| `focus`      | 选取当前正在获取焦点的元素     | 集合元素 |

**二、内容过滤选择器**

| 选择器            | 描述                             | 返回     |
| ----------------- | -------------------------------- | -------- |
| `:contains(text)` | 选取含有文本内容为text的元素     | 集合元素 |
| `:empty`          | 选取不包含子元素获取文本的空元素 | 集合元素 |
| `:has(selector)`  | 选择含有选择器所匹配的元素的元素 | 集合元素 |
| `:parent`         | 选取含有子元素或者文本的元素     | 集合元素 |

**三、可见过滤选择器**

| 选择器     | 描述                 | 返回     |
| ---------- | -------------------- | -------- |
| `:hidden`  | 选择所有不可见的元素 | 集合元素 |
| `:visible` | 选取所有可见的元素   | 集合元素 |

**四、属性过滤选择器**

| 选择器              | 说明                            | 返回     |
| ------------------- | ------------------------------- | -------- |
| `[attribute]`       | 选取拥有此属性的元素            | 集合元素 |
| `[attribute=value]` | 选取属性值为`value`值的元素     | 集合元素 |
| `[attribue^=value]` | 选取属性的值以`value`开始的元素 | 集合元素 |
| `[attribue$=value]` | 选取属性的值以`value`结束的元素 | 集合元素 |

**五、子元素过滤选择器**

| 选择器                       | 说明                                                         | 返回     |
| ---------------------------- | ------------------------------------------------------------ | -------- |
| `:nth-child(index/even/odd)` | 选取每个父元素下的第index个子元素或者奇偶元素（`index`从`1`算起） | 集合元素 |
| `:first-child`               | 选取每个元素的第一个子元素                                   | 集合元素 |
| `:last-child`                | 选取每个元素的最后一个子元素                                 | 集合元素 |

`nth-child()`选择器是很常用的子元素过滤选择器，如下

1. `:nth-child(even)`选择每个父元素下的索引值是偶数的元素
2. `:nth-child(odd)`选择每个父元素下的索引值是奇数的元素
3. `:nth-child(2)`选择每个父元素下的索引值是`2`的元素
4. `:nth-child(3n)`选择每个父元素下的索引值是3的倍数的元素 (`n`从`1`开始)



**六、表单选择器**

| 选择器      | 说明                                             |
| ----------- | ------------------------------------------------ |
| `:input`    | 选取所有`input` `textarea` `select` `button`元素 |
| `:text`     | 选取所有单行文本框                               |
| `:password` | 选取所有密码框                                   |
| `:radio`    | 选取所有单选框                                   |
| `:checkbox` | 选取所有多选框                                   |
| `:submit`   | 选取所有的提交按钮                               |
| `:image`    | 选取所有的图像按钮                               |
| `:reset`    | 选取所有的重置按钮                               |
| `:button`   | 选取所有的按钮                                   |
| `:file`     | 选取所有的上传域                                 |
| `:hidden`   | 选取所有的不可见元素                             |

**七、特定位置选择器**

- `:first`
- `:last`
- `:eq(index)`

**八、指定范围选择器**

- `:even`
- `:odd`
- `:gt(index)`
- `:lt(index)`

**九、排除选择器**

- `:not` 非

**十、使用过滤器**

- `jQuery`提供了`2`种选择文档元素的方式：选择器和过滤器

  ​    a. 类过虑器：根据元素的类属性来进行过滤操作。

  - `hasClass(className)`：判断当前`jQuery`对象中的某个元素是否包含指定类名，包含返回`true`，不包含返回`false`

  ​    b. 下标过滤器：精确选出指定下标元素

  - `eq(index)`：获取第`N`个元素。`index`是整数值，下标从`0`开始

     c. 表达式过滤器

  - `filter(expr)/(fn)`：筛选出与指定表达式/函数匹配的元素集合。
  - 功能最强大的表达式过滤器，可接收函数参数，也可以是简单的选择器表达式

    d. 映射 `map(callback)`：将一组元素转换成其他数组

    e. 清洗 `not(expr)`：删除与指定表达式匹配的元素

     f. 截取 `slice(start,end)`：选取一个匹配的子集

**十一、查找**

 向下查找后代元素

- `children()`:取得所有元素的所有子元素集合（子元素）
- `find()`:搜索所有与指定表达式匹配的元素(所有后代元素中查找)

查找兄弟元素 `siblings()`查找当前元素的兄弟

#### jQuery中DOM操作

 **获得内容 - text()、html() 以及 val()**

- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值

**插入节点**

| 方法             | 说明                             |
| ---------------- | -------------------------------- |
| `append()`       | 向每个匹配元素内部追加内容       |
| `appendTo()`     | 颠倒`append()`的操作             |
| `prepend()`      | 向每个匹配元素的内容内部前置内容 |
| `prependTo()`    | 颠倒`prepend()`的操作            |
| `after()`        | 向每个匹配元素之后插入内容       |
| `insertAfter()`  | 颠倒`after()`的操作              |
| `before()`       | 在每个匹配元素之前插入内容       |
| `insertBefore()` | 颠倒`before()`的操作             |

**删除节点**

jQuery提供了三种删除节点的方法 `remove()` `detach()` `empty()`

**`remove()`**

当某个节点用此方法删除后，该节点所包含的所有后代节点将同时被删除，用`remove()`方法删除后，还是可以继续使用删除后的引用

**`detach()`**

- 和`remove()`方法一样，也是从`DOM`中去掉所有匹配的元素，与`remove()`不同的是，所有绑定的事件、附加的数据等，都会被保留下来

**`empty()`**

- `empty()`方法并不是删除节点，而是清空节点，它能清空元素中所有后代节点

**复制节点**

- 使用`clone()`方法来完成
- 在`clone()`方法中传递一个参数`true`，同时复制元素中所绑定的事件

**替换节点**

- `jQuery`提供相应的方法 `replaceWidth()`

**样式操作**

- 获取样式和设置样式 `attr()`
- 追加样式 `addClass()`
- 移除样式 `removeClass()`
- 切换样式
  - `toggle()`方法只要是控制行为上的重复切换（如果元素是显示的，则隐藏；如果元素原来是隐藏的，则显示）
  - `toggleClass()`方法控制样式上的重复切换（如何类名存在，则删除它，如果类名不存在，则添加它）
- 判断是否含有某个样式
  - `hasClass()`可以用来判断元素是否含有某个`class`,如有返回`true` 该方法等价于`is()`

**设置和获取HTML、文本和值**

- `html()`

  - 此方法类似`JavaScript`中`innerHTML`属性，可以用来读取和设置某个元素中的`HTML`内容

- `text()`

  方法

  - 此方法类型`JavaScript`中`innerHTML`，用来读取和设置某个元素中的文本内容

**`val()`**方法

- 此方法类似`JavaScript`中的`value`属性，用来设置获取元素的值。无论是文本框、下拉列表还是单选框，都可以返回元素的值，如果元素多选，返回一个包含所有选择的值的数组

**遍历节点**

**`children()`**方法

方法

- 该方法用来取得匹配元素的子元素集合
- `children()`方法只考虑子元素而不考虑其他后代元素

**`next()`**方法

- 该方法用于取得匹配元素后面紧邻的同辈元素

**`prev()`**方法

- 用于匹配元素前面紧邻的同辈元素

**`siblings()`**方法

- 用于匹配元素前后所有的同辈元素

**`parent()`**方法

- 获得集合中每个 元素的父级元素

**`parents()`**方法

- 获得集合中每个元素的祖先元素



####  jQuery动画

**显隐动画**

- `show()`:显示 `hide()`:隐藏

  - 原理：`hide()`通过改变元素的高度宽度和不透明度，直到这三个属性值到`0`

  - `show()`从上到下增加元素的高度，从左到右增加元素宽度，从`0`到`1`增加透明度，直至内容完全可见

  - 参数：

    - ```
      show(speed,callback)
      ```

      - `speed`: 字符串或数字，表示动画将运行多久（`slow=0.6`/`normal=0.4`/`fast=0.2`）
      - `callback`: 动画完成时执行的方法

- 显示和隐藏式一对密不可分的动画形式

- **显隐切换**

  toggle():切换元素的可见状态

  - 原理：匹配元素的宽度、高度以及不透明度，同时进行动画，隐藏动画后将`display`设置为`none`
  - 参数：
    - `toggle(speed)`
    - `toggle(speed,callback)`
    - `toggle(boolean)`
      - `speed`: 字符串或数字，表示动画将运行多久（`slow=0.6`/`normal=0.4`/`fast=0.2`）
      - `easing`： 使用哪个缓冲函数来过渡的字符串(`linear`/`swing`)
      - `callback`： 动画完成时执行的方法
      - `boolean`:`true`为显示 `false`为隐藏

**滑动**

- **显隐滑动效果**
- `slideDown()`:滑动隐藏
- `slidUp()`:滑动显示
- 参数:
  - `slideDown(speed,callback)`
  - `slidUp(speed,callback)`
- **显隐切换滑动**
  - `slideToggle()`:显隐滑动切换
  - 参数:
    - `slidUp(speed,callback)`

**渐变：通过改变不透明度**

- **淡入淡出**
  - `fadeIn()`
  - `fadeOut()`
  - 参数：
    - `fadeIn(speed,callback)`
    - `fadeOut(speed,callback)`
- **设置淡出透明效果**
  - `fadeTo()`：以渐进的方式调整到指定透明度
  - 参数：
    - `fadeTo(speed,opacity,callback)`
- **渐变切换:结合`fadeIn`和`fadeOut`**
  - `fadeToggle()`
  - 参数:
    - `fadeOut(speed,callback)`

- **自定义动画：`animate()`**

  - 注意：在使用`animate`方法之前，为了影响该元素的`top`  `left` `bottom`  `right`样式属性，必须先把元素的`position`样式设置为`relative`或者`absolute`

  - 停止元素的动画

    - 很多时候需要停止匹配正在进行的动画，需要使用stop()

    - stop()语法结构：

      ```
      stop([clearQueue],[gotoEnd]);
      ```

      - 都是可选参数，为布尔值
      - 如果直接使用`stop()`方法，会立即停止当前正在进行的动画

  - 判断元素是否处于动画状态

    - 如果不处于动画状态，则为元素添加新的动画，否则不添加
       `if(!$(element).is(":animated")){ //判断元素是否处于动画状态}`
    - 这个方法在`animate`动画中经常被用到，需要注意

  - 延迟动画

    - 在动画执行过程中，如果你想对动画进行延迟操作，那么使用`delay()`

- 用`animate`模拟`show()`:

  - `show`: 表示由透明到不透明
  - `toggle`: 切换
  - `hide`:表示由显示到隐藏

- **动画方法总结**

| 方法名                     | 说明                                                         |
| -------------------------- | ------------------------------------------------------------ |
| `hide()`和`show()`         | 同时修改多个样式属性即高度和宽度和不透明度                   |
| `fadeIn()`和`fadeOut()`    | 只改变不透明度                                               |
| `slideUp()`和`slideDown()` | 只改变高度                                                   |
| `fadeTo()`                 | 只改变不透明度                                               |
| `toggle()`                 | 用来代替`show()`和`hide()`方法，所以会同时修改多个属性即高度、宽度和不透明度 |
| `slideToggle()`            | 用来代替`slideUp`和`slideDown()`方法，所以只能改变高度       |
| `fadeToggle()`             | 用来代替`fadeIn()`和`fadeOut`方法，只能改变不透明度          |
| `animate()`                | 属于自定义动画，以上各种动画方法都是调用了`animate`方法。此外，用`animate`方法还能自定义其他的样式属性，例如：`left` `marginLeft ``scrollTop`等 |

#### jQuery中的事件

**事件对象的属性**

- `event.type`：获取事件的类型
- `event.target`:获取到触发事件的元素
- `event.preventDefault`方法 阻止默认事件行为
- `event.stopPropagation()`阻止事件的冒泡
- `keyCode`：只针对于`keypress`事件，获取键盘键数字 按下回车，`13`
- `event.pageX / event.pageY` 获取到光标相对于页面的`x`坐标和`y`坐标
  - 如果没有`jQuery`，在IE浏览器中用`event.x` / `event.y`;在`Firefox`浏览器中用`event.pageX` / `event.pageY`。如果页面上有滚动条还要加上滚动条的宽度和高度
- `event.clientX`：光标对于浏览器窗口的水平坐标  浏览器
- `event.clientY`：光标对于浏览器窗口的垂直坐标
- `event.screenX`：光标对于电脑屏幕的水平坐标    电脑屏幕
- `event.screenY`：光标对于电脑屏幕的水平坐标
- `event.which` 该方法的作用是在鼠标单击事件中获取到鼠标的左、中、右键，在键盘事件中的按键 `1`代表左键  `2`代表中键  `3`代表右键

**事件冒泡**

- 什么是冒泡
  - 在页面上可以有多个事件，也可以多个元素影响同一个元素
  - 从里到外
  - 嵌套关系
  - 相同事件
  - 其中的某一父类没有相同事件时,继续向上查找
- 停止事件冒泡
  - 停止事件冒泡可以阻止事件中其他对象的事件处理函数被执行
  - 在`jQuery`中提供了**`stopPropagation()`**方法
- 阻止默认行为
  - 网页中元素有自己的默认行为，例如：单击超链接后会跳转、单击提交后表单会提交，有时需要阻止元素的默认行为
  - 在`jQuery`中提供了`preventDefault()`方法来阻止元素的默认行为

**事件捕获**

- 事件捕获和冒泡是相反的过程，事件捕获是从最顶端往下开始触发
- 并非所有的浏览器都支持事件捕获，并且这个缺陷无法通过`JavaScript`来修复。`jQuery`不支持事件捕获，如需要用事件捕获，要用原生的`JavaScript`

**`bind()`;绑定**

- 为匹配元素绑定处理方法
- 需要给一个元素添加多个事件 ，事件执行一样时候
- `one()`：只执行一次

- **绑定特定事件类型方法**：

| 分类     | 方法名称                                | 说明                                         |
| -------- | --------------------------------------- | -------------------------------------------- |
| 页面载入 | `ready(fn)`                             | 当`DOM`载入就绪可以绑定一个要执行的函数      |
| 事件绑定 | `blind(type,[data],fn)`                 | 为每个匹配元素的特定事件绑定一个事件处理函数 |
| 事件绑定 | `unblind()`                             | 解除绑定                                     |
| 事件绑定 | `on(events,[,selector[,]data],handler)` | 在选择元素上绑定一个或者多个事件处理函数     |
| 事件绑定 | `off()`                                 | 移除`on`绑定的事件                           |
| 事件绑定 | `delegate(selector,eventType,handler)`  | 为所有选择匹配元素附加一个或多个事件处理函数 |
| 事件绑定 | `undelegate()`                          | 移除绑定                                     |
| 事件动态 | `live(type,fn)`                         | 对动态生成的元素进行事件绑定                 |
| 事件动态 | `die(type,fn)`                          | 移除`live()`绑定的事件                       |
| 交互事件 | `hover()`                               | 鼠标移入移出                                 |
| 交互事件 | `toggle(fn1,fn2,[fn3],[fn4])`           | 每单击后依次调用函数                         |
| 交互事件 | `blur(fn)`                              | 触发每一个匹配元素的`blur`事件               |
| 交互事件 | `change()`                              | 触发每一个匹配元素的`change`事件             |
| 交互事件 | `click()`                               | 触发每一个匹配元素的`click`事件              |
| 交互事件 | `focus()`                               | 触发每一个匹配元素的`focus`事件              |
| 交互事件 | `submit()`                              | 触发每一个匹配元素的`submit`事件             |
| 键盘事件 | `keydown()`                             | 触发每一个匹配元素的`keydown`事件            |
| 键盘事件 | `keypress()`                            | 触发每一个匹配元素的`keypress`事件           |
| 键盘事件 | `keyup()`                               | 触发每一个匹配元素的keyup事件                |
| 鼠标事件 | `mousedown(fn)`                         | 绑定一个处理函数                             |
| 鼠标事件 | `mouseenter(fn)`                        | 绑定一个处理函数                             |
| 键盘事件 | `mouseleave(fn)`                        | 绑定一个处理函数                             |
| 键盘事件 | `mouseout(fn)`                          | 绑定一个处理函数                             |
| 键盘事件 | `mouseover(fn)`                         | 绑定一个处理函数                             |
| 窗口操作 | `resize(fn)`                            | 绑定一个处理函数                             |
| 窗口操作 | `scroll(fn)`                            | 绑定一个处理函数                             |

###### on注册事件

on注册简单事件

```JavaScript
// 表示给$(selector)绑定事件，并且由自己触发，不支持动态绑定。 $(selector).on( "click", function() {});
```

on注册委托事件

```JavaScript
// 表示给$(selector)绑定代理事件，当必须是它的内部元素span才能触发这个事件，支持动态绑定 $(selector).on( "click",“span”, function() {});
```

on注册事件的语法：

```JavaScript
// 第一个参数：events，绑定事件的名称可以是由空格分隔的多个事件（标准事件或者自定义事件） // 第二个参数：selector, 执行事件的后代元素（可选），如果没有后代元素，那么事件将有自己执行。 // 第三个参数：data，传递给处理函数的数据，事件触发的时候通过event.data来使用（不常使用） // 第四个参数：handler，事件处理函数 $(selector).on(events[,selector][,data],handler);
```

###### 事件解绑

```JavaScript
// 解绑匹配元素的所有事件 $(selector).off(); // 解绑匹配元素的所有click事件 $(selector).off("click");
```

#### jquery中的ajax

`jquery`对`Ajax`操作进行了封装，在`jquery`中的`$.ajax()`方法属于最底层的方法，第`2`层是`load()`、`$.get()`、`$.post();`第`3`层是`$.getScript()`、`$.getJSON()`，第`2`层使用频率很高

###### `load()`方法

------

- `load()`方法是`jquery`中最简单和常用的`ajax`方法，能载入远程`HTML`代码并插入`DOM`中 结构为：`load(url,[data],[callback])`
- 使用`url`参数指定选择符可以加载页面内的某些元素 `load`方法中`url`语法：`url selector` 注意：`url`和选择器之间有一个空格
- 传递方式
  - `load()`方法的传递方式根据参数`data`来自动指定，如果没有参数传递，则采用`GET`方式传递，反之，采用`POST`
- 回调参数
  - 必须在加载完成后才执行的操作，该函数有三个参数 分别代表请求返回的内容、请求状态、`XMLHttpRequest`对象
  - 只要请求完成，回调函数就会被触发

```javascript
$("#testTest").load("test.html",function(responseText,textStatus,XMLHttpRequest){
    //respnoseText 请求返回的内容
    //textStatus 请求状态 ：sucess、error、notmodified、timeout
    //XMLHttpRequest 
})
```

**.load方法参数**

| 参数名称         | 类型       | 说明                                         |
| ---------------- | ---------- | -------------------------------------------- |
| `url`            | `String`   | 请求`HTML`页面的`URL`地址                    |
| `data(可选)`     | `Object`   | 发送至服务器的`key` / `value`数据            |
| `callback(可选)` | `Function` | 请求完成时的回调函数，无论是请求成功还是失败 |

######  $.get和$.post方法

------

`load()`方法通常用来从web服务器上获取静态的数据文件。在项目中需要传递一些参数给服务器中的页面，那么可以使用`$.get()`和`$.post()`或`$.ajax()`方法

- 注意：`$.get()`和`$.post()`方法是`jquery`中的全局函数

- **$.get()方法**

  - `$.get()`方法使用`GET`方式来进行异步请求

  - 结构为：

    ```
    $.get(url,[data],callback,type)
    ```

    - 如果服务器返回的内容格式是`xml`文档，需要在服务器端设置`Content-Type`类型 代码如下：`header("Content-Type:text/xml:charset=utf-8")` //`php`

- **`$.get()`方法参数解析**

| 参数             | 类型       | 说明                                                         |
| ---------------- | ---------- | ------------------------------------------------------------ |
| `url`            | `String`   | 请求`HTML`页的地址                                           |
| `data(可选)`     | `Object`   | 发送至服务器的`key`/ `value` 数据会作为`QueryString`附加到请求URL中 |
| `callback(可选)` | `Function` | 载入成功的回调函数（只有当`Response`的返回状态是success才调用该方法） |
| `type(可选)`     | `String`   | 服务器返回内容的格式，包括`xml`、`html`、`script`、`json`、`text`和`_default` |

**$.post()方法**

- 它与$.get()方法的结构和使用方式相同，有如下区别
  - `GET`请求会将参数跟张乃URL后进行传递，而`POST`请求则是作为`Http`消息的实体内容发送给web服务器，在`ajax`请求中，这种区别对用户不可见
  - `GET`方式对传输数据有大小限制（通常不能大于`2KB`），而使用`POST`方式传递的数据量要比`GET`方式大得多（理论不受限制）
  - `GET`方式请求的数据会被浏览器缓存起来，因此其他人可以从浏览器的历史纪录中读取这些数据，如：账号、密码。在某种情况下，`GET`方式会带来严重的安全问题，而`POST`相对来说可以避免这些问题
  - `GET`和`POST`方式传递的数据在服务端的获取也不相同。在`PHP`中，`GET`方式用`$_GET[]`获取；`POST`方式用`$_POST[]`获取;两种方式都可用`$_REQUEST[]`来获取

**总结**

- 使用`load()`、`$.get()`和`$.post()`方法完成了一些常规的`Ajax`程序，如果还需要复杂的`Ajax`程序，就需要用到`$.ajax()`方式



###### $.ajax()方法

------

- `$.ajax()`方法是`jquery`最底层的`Ajax`实现，它的结构为`$.ajax(options)`
- 该方法只有一个参数，但在这个对象里包含了`$.ajax()`方式所需要的请求设置以及回调函等信息，参数以`key` / `value`存在，所有参数都是可选的

- **$.ajax()方式常用参数解析**

| 参数         | 类型       | 说明                                                         |
| ------------ | ---------- | ------------------------------------------------------------ |
| `url`        | `String`   | (默认为当前页地址)发送请求的地址                             |
| `type`       | `String`   | 请求方式（`POST`或`GET`）默认为`GET`                         |
| `timeout`    | `Number`   | 设置请求超时时间（毫秒）                                     |
| `dataType`   | `String`   | 预期服务器返回的类型。可用的类型如下<br /><br /> **xml**:返回`XML`文档，可用`jquery`处理<br />**html**:返回纯文本的`HTML`信息，包含的`script`标签也会在插入`DOM`时执行<br />**script**：返回纯文本的`javascript`代码。不会自动缓存结果，除非设置`cache`参数。注意：在远程请求时，所有的`POST`请求都将转为`GET`请求<br />**json**:返回`JSON`数据<br />**jsonp**:`JSONP`格式，使用`jsonp`形式调用函数时，例如：`myurl?call back=?,jquery`将自动替换后一个`？`为正确的函数名，以执行回调函数<br />**text**:返回纯文本字符串 |
| `beforeSend` | `Function` | 发送请求前可以修改`XMLHttpRequest`对象的函数，例如添加自定义`HTTP`头。在`beforeSend`中如果返回`false`可以取消本次`Ajax`请求。`XMLHttpRequest`对象是唯一的参数<br /> function(XMLHttpRequest){<br />          `this`;//调用本次`Ajax`请求时传递的`options`参数 } |
| `complete`   | `Function` | 请求完成后的回调函数（请求成功或失败时都调用）<br />参数：`XMLHttpRequest`对象和一个描述成功请求类型的字符串<br />function(XMLHttpRequest,textStatus){          `this`;//调用本次Ajax请求时传递的`options`参数 } |
| `success`    | `Function` | 请求成功后调用的回调函数，有两个参数<br />(1)由服务器返回，并根据`dataTyppe`参数进行处理后的数据<br />(2)描述状态的字符串<br />`function`(data,textStatus){          //`data`可能是`xmlDoc、``jsonObj`、`html`、`text`等          `this`;//调用本次`Ajax`请求时传递的`options`参数<br />} |
| `error`      | `Function` | 请求失败时被调用的函数                                       |
| `global`     | `Boolean`  | 默认为`true`。表示是否触发全局`Ajax`事件，设置为`false`将不会触发。`AjaxStart`或`AjaxStop`可用于控制各种`Ajax`事件 |







