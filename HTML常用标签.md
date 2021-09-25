# Html 常用标签
html常用的标签有很多，本文主要介绍三个标签**a**标签，**img**标签，**table**标签。

## 一、a标签
<a></a>标签中的a是anchor的缩写，anchor是锚的意思，可以通过a标签的href（hyper reference的缩写）属性创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他URL的超链接

1. a标签的常用属性  
   href：hyper reference的缩写,通过指定此属性可以跳转到其他网页，内部锚点，邮箱或者电话  
   target：规定在何处打开链接文档
2. a标签的作用  
   - 跳转到外部页面
   - 跳转到内部锚点
   - 跳转到电话或邮箱
3. href的取值  
   1. 网址
       - https://google.com
       - http://google.com
       - //google.com
   2. 路径  
       + /a/b/c绝对路径 a/b/c 相对路径
       + index.html ./index.html
   3. 伪协议
       + javascript:代码；
       + mailto:邮箱
       + tel:手机号
   4. id
       + href=#xxx 
4.  target的取值  
    1.  _blank：在空白页打开
    2.  _top：当有多个iframe嵌套时，在最顶层窗口打开链接
    3.  _parent：在父窗口中打开链接
    4.  _self：在当前窗口中打开链接
    5.  自己命名name：如果存在此name的窗口，则在此窗口中打开，如果不存在则创建一个以此命名的窗口并在此窗口中打开


## 二、img标签
  1.  作用：发出get请求，展示一张图片
  2.  常用的属性  
       +  alt：对图像的文本描述，当由于一些原因无法加载图像时，浏览器会显示alt属性中的文本  
       +  height: 图像的高度
       +  width：图像的宽度
       +  src：图像的url
  3.  图像加载过程中的事件  
       +  onload: 当图片加载成功时调用此事件
       +  onerror: 当图片加载失败时调用此事件
  
## 三、table标签
  1. 作用：以表格的形式展示数据
  2. 相关的标签  
     +  table
     +  thead：表头
     +  tbody：表格主体
     +  tfoot：表格页脚
     +  tr：table row 表的行
     +  th：table header cell 表头单元格
     +  td：table data cell 表格数据
        ```
        <table border=1>
            <thead>
                <tr>
                    <th>姓名</th>
                    <th>语文</th>
                    <th>数学</th>
                    <th>英语</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>小明</td>
                    <td>99</td>
                    <td>88</td>
                    <td>44</td>
                </tr>
                <tr>
                    <td>小红</td>
                    <td>44</td>
                    <td>55</td>
                    <td>33</td>
                </tr>
                <tr>
                    <td>小黑</td>
                    <td>54</td>
                    <td>67</td>
                    <td>77</td>
                </tr>
            </tbody>
        </table>
  3.  相关的样式  
       +  table-layout:单元格行列的算法规则。**automatic**：默认，列宽度由单元格内容设定（按照单元格内容自动设置宽度），**fixed**，列宽由表格宽度和列宽度设定(由width属性指定)
       +  border-collapse：用来决定表格的边框是分开的还是合并的.**collapse** 相邻的单元格共用同一条边框 **separate** 默认值。每个单元格拥有独立的边框
       +  border-spacing:属性指定相邻单元格边框之间的距离（只适用于 边框分离模式 ）