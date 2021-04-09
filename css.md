## 一、基础知识
### 1、css单位
（1）px<br>
（2）%
  
    width、height、font-size的百分比是相对于父元素“相同属性”的值计算
    line-height的百分比相对于当前元素的font-size值来计算的
    vertical-align的百分比相对于当前元素的lin-height值决定的
（3）em：1em= `“当前元素”的font-size值` <br>
若当前元素的font-size值没有定义，则当前元素会继承父元素的font-size；若所有祖先元素都没有定义font-size，则当前元素继承浏览器默认的font-size（16px）
  
    使用技巧：
    1、首行缩进使用 text-indent: 2em
    2、使用em作为统一单位
    html{ font-size: 62.5% } //设置html标签的元素字体大小为 62.5% * 16px = 10px
    这时1em = 10px
（4）rem：相对于根元素（html元素）的字体大小。`rem布局是移动端最常见的布局方式之一`
### 2、css特性：继承性、层叠性
（1）继承性：子元素继承父元素的某些样式属性

    文本相关属性：font...、line-height、text-align、text-indent、word-spacing
    列表相关属性：list-style-image、list-style-position、list-style-type、list-style
    颜色相关属性：color
注：a元素本身有默认的颜色样式，优先级比继承的颜色要高。若想a元素也能继承父元素的颜色，可在a元素中使用" color: inherit; " <br>
（2）层叠性 ：样式的覆盖。对一个元素，若重复定义了多个相同的属性，`且这些样式具有相同的权重时`，css会以最后定义的属性值为准。（“后来者居上原则”）<br>
即要满足：`元素相同、属性相同、权重相同`
### 3、css优先级
css：层叠样式表，层叠指的就是样式的覆盖。当样式的覆盖发生冲突时，以优先级高的为准

    常见的五种样式冲突：
    1、引用方式冲突  行内样式 > (内部样式 = 外部样式) 
    若内部样式与外部样式同时存在，则以最后引用的样式为准（“后来者居上原则”）
    2、继承方式冲突  “最近的祖先元素”获胜
    3、指定样式冲突  当直接指定"当前元素"的样式发生冲突时， 样式权重高的获胜
       行内样式 > id选择器 > class选择器 > 元素选择器 
       class选择器优先级 = 属性选择器 = 伪类（如：hover、:first-child）
       元素选择器优先级 = 伪元素（::before、::after、::first-letter、::first-line）
    4、继承样式和指定样式冲突  指定样式获胜
    5、!important 优先级最高
    如何覆盖!important：使用相同的选择器，再添加一条!important的css语句，但这条语句得放在后面（“后来者居上”）
                        使用优先级更高的选择器，再添加一条!important的css语句
### 4、css的引用方式
外部样式表多用于公有样式，内部样式表多用于私有样式，行内样式表多用于小修改或者优先级方面
### 5、css的层次选择器
    M N  后代选择器，选择M元素内部后代的N元素（所有N元素）   
    M>N  子代选择器，选择M元素内部子代的N元素（所有第一级N元素）
    M~N  兄弟选择器，选择M元素后“所有”的同级N元素
    M+N  相邻选择器，选择M元素相邻的“下一个”同级N元素
    :first-letter  选中元素内容中的“第一个字”或“第一个字母”
    :first-line  选中元素内容中的“第一行文字”
## 二、css规范
### 1、命名规范
文件名：reset.css用于去除元素的默认样式，使得所有浏览器页面的外观保持统一 <br>
id和class名：推荐用中划线，其中为避免class命名的重复，命名时一般取父元素的class名作为前缀       
注：reset.css必须在其他css代码前引入
## 三、盒子模型
margin外边距 - border边框 - padding内边距 - content内容区
### 1、内容区
有width、height、overflow3个属性<br>
width和height是针对内容区而言，不包括padding；当内容区信息太多超出内容区所占范围时，可使用overflow溢出属性来指定处理方法（eg：overflow-y: scroll; overflow: hidden）
### 2、内边距
padding: 上 右 下 左
### 3、外边距
#### （1）外边距叠加
当两个`垂直外边距` `相遇`时，这两个外边距将会合并为一个。叠加后的高度为叠加前两个外边距中的最大值

    1、同级元素：垂直外边距相遇时叠加
    2、父子元素：当一个元素包含在另一个元素中，父元素没有padding或border把子元素的外边距隔开，父子元素的相邻上下外边距发生合并
注：外边距叠加针对的是block和inline-block元素    
#### （2）负margin技术 

### 4、边框






    