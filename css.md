# css
## 基础
### css: 层叠样式表
###标记简史
> * 早期的web仅仅是链接,使用html添加基本的格式和结构
> * 随着万维网的流行，html开始表示页面和视觉（字体，粗细、表格）。表格成为一个布局方式而非数据展示方式
> * 页面越来越丰富，代码却越来越难维护，bug定位困难
> * web设计一团糟
> * css 出现了，将文档的表现和内容分开

### id 类名
> * 应该根据“他们是什么”来为元素命名，而不是“他们的外观如何”
> * 浏览器区分名字的大小写，因为id和类名完全小写，多个单词用“-”连接

### id还是类
常常很难决定一个元素使用id还是类，一般原则是类应该使用于概念上类似的元素，id使用于唯一元素  
为了将不必要的标记减到最少，应该只在没有现有元素能够实现区域分割的情况下使用div，列如使用列表，就不需要包含在div中  

```
<div class="nav">
 <ul>
   <li>list1</li>
   <li>list2</li>
 </ul>
</div>
```   

可以直接删除div  
```
<ul class="nav">
  <li>list1</li>
  <li>list2</li>
</ul>
```  

### 不同的html和css版本
DTD 文档类型定义 DOCTYPE  
W3C验证器  

- <http://validator.w3.org>  
- <http://favelets.com>  


## selector
### 常用的选择器
 1. 类型选择器
 类型选择器用来选择特定类型的元素，比如段落或者标题 
  
 ```
 p {color:black;}
 h1 {font-weight:bold;}
 ```  
 
 2. 后代选择器  
 用来寻找特定元素或者元素组的后代，由选择器直接的空格表示  
 ```
 blockquote p {padding-left:2em;}
 ```  
 
 3. id选择器和类选择器   
 id选择器由#表示  
 类选择器由点.表示  
 ```
 #intro {font-weight:bold;} 
 .data-post {color:#ccc;}
 ``` 
 4. 伪类  
 根据文档结构之外的其他条件对元素应用样式，例如表单元素或链接的状态  
 
 ```
 
 /* make all unvisited links blue */  
 
 a:link {color:blue;}  
 
 /* make all visited links green */
 a:visited {color:green}  
 
 /* make links red when hovered or activated.focus is added for keyboard support */
 a:hovered,a:focus,a:active {color:red;}
 
 /* make tables row red when hovered over*/
 tr:hoverd {backgroud-color:red;}
 
 ```
 
 :link和:visited称为链接伪类，只能应用于锚元素，:hover,:active和:focus 称为动态伪类，理论上可以应用于所以元素  
 
 5.通用选择器  
 通用选择器可以匹配任何元素，就像通配符  
 ```
 *{
   padding:0;
   margin:0;
 }	
 ```
 
 6.子选择器和相邻同胞选择器
 
 后代选择器选择一个元素的所有后代，而子选择器只选择元素的直接后代，如下，外层列表的列表项显示一个定制的图标，而嵌套列表中的列表项不受影响  
 ```
 #nav>li{
 background:url(folder.png) no-repeat left top;
 padding-left:20px;
 }
 
 <ul id="nav">
   <li>home</li>
   <li>
      <ul>
        <li>desigin</li>
      </ul>
   </li>
</ul>	
```  

相邻同胞选择器可用于定位同一个父元素下某个元素之后的元素  
```
h2 + p {color:#777;}

<h2>sss</h2>
  <p> aaa</p>
  <p>bbb</p>
```

7.属性选择器  
```
<p> this is <acronym title="self" > a test </acronym> for example </p>

acronym[title]{
 border-bottom:1px dotted #999;
}

acronym[title]:hover,acronym[title]:focus{
 cursor:help;
}
```  
  
## css导入和设计代码结构      
html内导入  
```
<style type ="text/css">
@import url("xx.css")
</style>
```

样式表内导入
```
@import url("xxx.css")
```  
结构
 
- 一般性样式
  - 主体样式
  - reset样式
  - 链接
  - 标题
  - 其他样式
- 辅助样式  
  - 表单
  - 通知和错误
  - 一致的条目
- 页面结构
  - 标题、页脚和导航
  - 布局
  - 其他页面元素结构
- 页面组件
  - 各个页面
- 覆盖      
  
  
