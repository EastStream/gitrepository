一级标题
===

二级标题
---

#一级标题
##二级标题
###三级标题
####四级标题
#####五级标题
######六级标题

段落的换行是使用两个以上空格加上回车？或者使用一个空行

空格&emsp;一个中文字符&ensp;半个中文字符&nbsp;半半个中文字符

*斜体文本1*
_斜体文本2_
**粗体文本1**
__粗体文本2__

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格
***
* * *
- - -
------

~~删除线~~
<u>下划线</u>

脚注[^脚注]
[^脚注]:脚注内容可以写在任意位置

列表
* 一
* 二
* 三

+ 一
+ 二
+ 三

- 一
- 二
- 三

1. 一
2. 二
3. 三

嵌套子列表前添加四个空格
* 一
    + 一一
    + 一二
    + 一三
* 二
* 三

>区块引用
>学的不仅是技术更是梦想

嵌套
>外层
>>第一层
>>>第二层

区块中使用列表
>1. 一
>2. 二
>* 一

列表中使用区块
1. 一
    >前添加四个空格的缩进
2. 二

代码块
`printf()`函数

代码区块使用 4 个空格或者一个制表符？

```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```

这是一个链接[baidu](http://www.baidu.com)或者<http://www.baidu.com>

高级链接
这个链接用1作为网址变量 [Google][1]
这个链接用baidu作为网址变量[Baidu][baidu]
然后在文档的结尾为变量赋值（空行空格）

  [1]: http://www.google.com
  [baidu]: http://www.baidu.com

![alt 属性文本](图片地址 "可选标题")
![alt 百度图标](https://www.baidu.com/img/flexible/logo/pc/result.png "baidu")

Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 <img> 标签。

<img src="https://www.baidu.com/img/flexible/logo/pc/result.png" width="50%">

Markdown 制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
我们可以设置表格的对齐方式：
* -: 设置内容和标题栏居右对齐。
* :- 设置内容和标题栏居左对齐。
* :-: 设置内容和标题栏居中对齐。

| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。
目前支持的 HTML 元素有：\<kbd> \<b> \<i> \<em> \<sup> \<sub> \<br>等 ，如：
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑

转义\

当你需要在编辑器中插入数学公式时，可以使用两个美元符 $$ 包裹 TeX 或 LaTeX 格式的数学公式来实现。提交后，问答和文章页会根据需要加载 Mathjax 对数学公式进行渲染。如：

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$

typora 画流程图、时序图(顺序图)、甘特图
* 横向流程图源码格式
    ```mermaid
    graph LR
    A[方形] -->B(圆角)
        B --> C{条件a}
        C -->|a=1| D[结果1]
        C -->|a=2| E[结果2]
        F[横向流程图]
    ```
* 竖向流程图源码格式：
    ```mermaid
    graph TD
    A[方形] --> B(圆角)
        B --> C{条件a}
        C --> |a=1| D[结果1]
        C --> |a=2| E[结果2]
        F[竖向流程图]
    ```
* 标准流程图源码格式：
    ```flow
    st=>start: 开始框
    op=>operation: 处理框
    cond=>condition: 判断框(是或否?)
    sub1=>subroutine: 子流程
    io=>inputoutput: 输入输出框
    e=>end: 结束框
    st->op->cond
    cond(yes)->io->e
    cond(no)->sub1(right)->op
    ```
* 标准流程图源码格式（横向）：
    ```flow
    st=>start: 开始框
    op=>operation: 处理框
    cond=>condition: 判断框(是或否?)
    sub1=>subroutine: 子流程
    io=>inputoutput: 输入输出框
    e=>end: 结束框
    st(right)->op(right)->cond
    cond(yes)->io(bottom)->e
    cond(no)->sub1(right)->op
    ```
* UML时序图源码样例：
    ```sequence
    对象A->对象B: 对象B你好吗?（请求）
    Note right of 对象B: 对象B的描述
    Note left of 对象A: 对象A的描述(提示)
    对象B-->对象A: 我很好(响应)
    对象A->对象B: 你真的好吗？
    ```
* UML时序图源码复杂样例：
    ```sequence
    Title: 标题：复杂使用
    对象A->对象B: 对象B你好吗?（请求）
    Note right of 对象B: 对象B的描述
    Note left of 对象A: 对象A的描述(提示)
    对象B-->对象A: 我很好(响应)
    对象B->小三: 你好吗
    小三-->>对象A: 对象B找我了
    对象A->对象B: 你真的好吗？
    Note over 小三,对象B: 我们是朋友
    participant C
    Note right of C: 没人陪我玩
    ```
* UML标准时序图样例：
    ```mermaid
    %% 时序图例子,-> 直线，-->虚线，->>实线箭头
    sequenceDiagram
        participant 张三
        participant 李四
        张三->王五: 王五你好吗？
        loop 健康检查
            王五->王五: 与疾病战斗
        end
        Note right of 王五: 合理 食物 <br/>看医生...
        李四-->>张三: 很好!
        王五->李四: 你怎么样?
        李四-->王五: 很好!
    ```
* 甘特图样例：
    ```mermaid
            gantt
            dateFormat  YYYY-MM-DD
            title 软件开发甘特图
            section 设计
            需求                      :done,    des1, 2014-01-06,2014-01-08
            原型                      :active,  des2, 2014-01-09, 3d
            UI设计                     :         des3, after des2, 5d
        未来任务                     :         des4, after des3, 5d
            section 开发
            学习准备理解需求                      :crit, done, 2014-01-06,24h
            设计框架                             :crit, done, after des2, 2d
            开发                                 :crit, active, 3d
            未来任务                              :crit, 5d
            耍                                   :2d
            section 测试
            功能测试                              :active, a1, after des3, 3d
            压力测试                               :after a1  , 20h
            测试报告                               : 48h
    ```