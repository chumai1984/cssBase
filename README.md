# 前端css规范
---

## 分类方法
1. CSS文件的分类和引用顺序
	1. 公共样式
    2. 特殊样式
    3. 皮肤样式 
    
2. CSS内部的分类及其顺序
	1. 重置（reset）和默认（base）（tags）：消除默认样式和浏览器差异，并设置部分标签的初始样式，以减少后面的重复劳动！你可以根据你的网站需求设置！
	2. 统一处理：建议在这个位置统一调用背景图（这里指多个布局或模块或元件共用的图）和清除浮动（这里指通用性较高的布局、模块、元件内的清除）等统一设置处理的样式！
	3. 布局（grid）（.g-）：将页面分割为几个大块，通常有头部、主体、主栏、侧栏、尾部等！
	4. 模块（module）（.m-）：通常是一个语义化的可以重复使用的较大的整体！比如导航、登录、注册、各种列表、评论、搜索等！
	5. 元件（unit）（.u-）：通常是一个不可再分的较为小巧的个体，通常被重复用于各种模块中！比如按钮、输入框、loading、图标等！
	6. 功能（function）（.f-）：为方便一些常用样式的使用，我们将这些使用率较高的样式剥离出来，按需使用，通常这些选择器具有固定样式表现，比如清除浮动等！不可滥用！
	7. 皮肤（skin）（.s-）：如果你需要把皮肤型的样式抽离出来，通常为文字色、背景色（图）、边框色等，非换肤型网站通常只提取文字色！非换肤型网站不可滥用此类！
	8. 状态（.z-）：为状态类样式加入前缀，统一标识，方便识别，她只能组合使用或作为后代出现（.u-ipt.z-dis{}，.m-list li.z-sel{}），具体详见命名规则的扩展相关项。
---

## 命名规则
1. 分类命名方法
    布局（grid）（.g-）
    模块（module）（.m-）
    元件（unit）（.u-）
    功能（function）（.f-）
    皮肤（skin）（.s-）
    状态（.z-）
 
2. 后代选择器命名
	长度大于等于2的类选择器为后代选择器
    .m-list li{}
    .m-list .text{}
    后代选择器不需要完整表现结构树层级，尽量能短则短。
    不要在页面布局中使用
  
3. 命名应简约而不失语义
    .m-list .wrap{}
    .g-side2{}
    
4. 相同语义的不同类命名
	.m-list、.m-list2、.m-list3等，都是列表模块，但是是完全不一样的模块
    
5. 模块和元件的扩展类的命名方法
    .m-list作为基类（可以单独使用）
    .m-list-1为扩展类（必须配合基类使用，m-list-"数字或字母"）
    .u-btn.z-dis{}  class="u-btn z-dis"

6. 模块和元件的后代选择器的扩展类
    后代选择器：.m-login .btn{}。
	后代选择器扩展：.m-login .btn-1{}，.m-login .btn-dis{}。
    同样也可以采取独立状态分类（.z-）方法：.m-login .btn.z-dis{}，然后像这样使用：class="btn z-dis"。

7. 分组选择器有时可以代替扩展方法
	两个元件共性的样式
	.u-tip1,.u-tip2{}
	.u-tip1 .itm,.u-tip2 .itm{}
    
8. 防止污染和被污染
	当模块或元件之间互相嵌套，应当注意样式被污染
    如果你的模块或元件可能嵌套或被嵌套于其他模块或元件，那么要慎用标签选择器，必要时采用类选择器，并注意命名方式
    可以采用.m-layer .layerxxx、.m-list2 .list2xxx的形式来降低后代选择器的污染性
---

























