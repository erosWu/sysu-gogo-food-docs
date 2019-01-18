# 代码规范

## JS规范
### 使用ES2016+
JavaScript规范使用[ES2016+][1]


### 使用ESLint
代码使用[ESlint][2]作为基本的语法检验工具，规则如下：
[Eslint Config Standard][3] 作为基础规则
[semi][4] 使用分号
[space-before-function-paren][5] 函数参数列表前需要有括号
[object-curly-spacing][6] 对象花括号中必须有空格
[arrow-parens][7] 箭头函数参数列表按需添加括号
[no-console][8] 不适用console
[camelcase][9] 允许非驼峰式命名
基于[JavaScript Standard Style][10]


额外规则：永远不省略分号
可以使用Async/Await的地方就不使用Promise
Vue组建名字采用pascal命名法，即首字母大写的驼峰式命名，如LoginBox.vue
组件文件和组件使用相同的名字，组件名必须避免使用Vue保留标签名（包括HTML标签和Vue内部标签）
JS变量名、参数名、函数名：必须使用camel命名法。命名同时还需要关注语义，如：

 - 变量名应当使用名词camel命名
 - boolean类型的应当使用is、has等起头,表示其类型
 - 函数名应当用动宾短语

## HTML规范
Store 中的Module 使用camel命名
Store 中的state/getters/action使用 camel 命名
Store 中的Mutation 使用全部大写的下划线命名法
HTML标签id、class命名使用camel命名
HTML标签中的属性必须用双引号包围

1.img标签要写alt标签 
2.单标签不要写闭合标签（img、link、input、hr、br） 
3.自定义属性要以data- 开头 
4.td要在tr里面，li要在ul/ol里面 
5.ul/ol的直接子元素只能是li 
6.section里面要有标题标签 
7.使用section标签增强SEO(搜索引擎优化) 
8.行内元素里面不可使用块级元素(a标签里面不能放div) 
9.每个页面要写 
10.要用table布局写邮件模板 
11.html要保持简洁，不要套太多层 
12.特殊情况下才在html里面写script和style 
13.样式要写在head标签里 
14.html要加上lang的属性

    <html lang="en">
    <html lang="zh-CN">

15.要在head标签靠前位置写上charset和meta标签 
16.特殊符号使用html实体
17.img空src的问题
18.关于行内元素空格和换行的影响 
19.类的命名使用小写字母加中划线（hello-world) 
20.不推荐使用自定义标签 
21.重复杂id和重复属性 
22.不推荐使用属性设置样式（canvas width height 需要写） 
23.使用合适的标签 
（1）如果内容是表格就使用table，table有自适应的优点；如果是一个列表就使用ol/ul标签，扩展性比较好 
（2）如果是输入框就使用input，而不是写一个p标签，然后设置contenteditable=true，因为这个在IOS Safari上光标定位容易出现问题。如果需要做特殊效果除外 
（3）如果是粗体就使用b/strong，而不是自己设置font-weight 
（4）如果是表单就使用form标签，注意form里面不能套form 
（5）如果是跳链就使用a标签，而不是自己写onclick跳转。a标签里面不能套a标签 
（6）使用html5语义化标签，如导航使用nav，侧边栏使用aside，顶部和尾部使用header/footer，页面比较独立的部分可以使用article，如用户的评论。 
（7）如果是按钮就应该写一个button或者`<input type="button">`，而不是写一个a标签设置样式，因为使用button可以设置disabled，然后使用CSS的:disabled，还有:active等伪类使用，例如在:active的时候设置按钮被按下去的感觉 
（8）如果是标题就应该使用标题标签h1/h2/h3，而不是自己写一个`<p class="title"></p>`，相反如果内容不是标题就不要使用标题标签了 
（9）在手机上使用select标签，会有原生的下拉控件，手机上原生select的下拉效果体验往往比较好，不管是IOS还是android，而使用`<input type="tel">`在手机上会弹一个电话号码的键盘，`<input type="number">` `<input type="email">`都会弹相应的键盘
（10）如果是分隔线就使用hr标签，而不是自己写一个border-bottom的样式，使用hr容易进行检查 
（11）如果是换行文本就应该使用p标签，而不是写br，因为p标签可以用margin设置行间距，但是如果是长文本的话使用div，因为p标签里面不能有p标签，特别是当数据是后端给的，可能会带有p标签，所以这时容器不能使用p标签。 
24.不要在https的链接里写http的图片

    <img src=”//static.chimeroi.com/hello-world.jpg”>

## CSS规范
使用[SCSS预处理器][11]


使用嵌套规则，嵌套规则下尽量使用直接子节点选择符防止预料之外的规则适用

    .parent {
        > .child1 { // good
            // styles
        }
        . child2 { // not good
            // styles
        }
    }
    .parent .child3 {} // not good

 长度单位使用rpx
 

 - see [this][12]


  [1]: http://kangax.github.io/compat-table/es2016plus/
  [2]: http://eslint.cn/
  [3]: https://github.com/standard/eslint-config-standard
  [4]: https://eslint.org/docs/rules/semi
  [5]: https://eslint.org/docs/rules/space-before-function-paren
  [6]: https://eslint.org/docs/rules/object-curly-spacing
  [7]: https://eslint.org/docs/rules/arrow-parens
  [8]: https://eslint.org/docs/rules/no-console
  [9]: https://eslint.org/docs/rules/camelcase
  [10]: https://github.com/standard/standard/blob/master/RULES.md#javascript-standard-style
  [11]: http://sass.bootcss.com/docs/sass-reference/
  [12]: https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html#%E5%B0%BA%E5%AF%B8%E5%8D%95%E4%BD%8D