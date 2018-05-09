markdown learning

#是什么？
Markdown 是一种轻量级标记语言
#做什么？
允许人们使用易读易写的纯文本格式编辑文档，然后转换成有效的XHTML文档。
#需要人群
markdown是为那些需要经常码字或者进行文字排版的、对码字手速和排版顺畅度有要求的人群设计的，
他们希望用键盘把文字内容啪啪啪地打出来后就已经排版好了，最好从头到尾都不要使用鼠标。
这些人包括经常需要写文档的码农、博客写手、网站小编、出版业人士
#怎么用？

##区块元素

###段落和换行

段落是由一个或多个连续的文本行组成，它的前后要有一个以上的**空行**  
Markdown 插入 `<br />` 标签换行的话，在插入处先按入两个以上的**空格**然后回车

###标题

Markdown 支持两种标题的语法，类 Setext 和类 atx 形式  
类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），例如：
    This is an H1
    =============
    
    This is an H2
    -------------
类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

    # 这是 H1

    ## 这是 H2

    ###### 这是 H6

###区块引用

先分好段落，然后在每行的最前面加上 \>
    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    > Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
    > 
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    > id sem consectetuer libero luctus adipiscing.
    
也可以省略，只在整个段落的第一行最前面加上 \>
    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    id sem consectetuer libero luctus adipiscing.
使用不同数量的`>`，可以嵌套使用区块引用
    
    >This is the first level of quoting.
    >
    > > This is nested blockquote.
    >
    > Back to the first level.

**注**：引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等

###列表

分为无序列表和有序列表。  
无序列表使用星号、加号或是减号作为列表标记
   
    *   Red
    *   Green
    *   Blue

有序列表则使用数字接着一个英文句点

    1.  Bird
    2.  McHale
    3.  Parish

**注：**数字大小并不会影响输出的 HTML 结果  

段首出现数字加英文句点，则需要反斜杠来区分

    1986\. What a great season.

###代码区块

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，
通常这些区块我们并不希望它以一般段落文件的方式去排版，
而是照原来的样子显示  
在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以  
在代码区块里面， & 、 < 和 > 会自动转成 HTML 实体

###分隔线

在一行中用三个以上的星号、减号、底线来建立一个分隔线，
行内不能有其他东西。你也可以在星号或是减号中间插入空格

    * * *

    ***

    *****

    - - -

    -------------------

##区段元素



###链接

markdown 支持两种链接语法

1. 行内式
    
    eg：this is an [example](http://example.com/ "Optinal Tile Here")  </br>
    组成方式: [显示内容]\(网址 "title"\)  </br>
    方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可

2. 参考式

    eg: this is an [example][id]  
    组成方式： [显示内容][链接标签]  
    链接内容： [链接标签]: 地址
    
        链接内容格式：
        方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
        接着一个冒号
        接着一个以上的空格或制表符
        接着链接的网址
        选择性地接着 title 内容，可以用单引号、双引号或是括弧包着

    特殊参看式---隐式链接，可以省略链接标签  
    eg: [Google][] link  
    \[Google\][]  
    [Google]: 网址
    
    **注**： 链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写

[id]: http://example.com/
[google]: http://google.com/
    
###强调

使用\* 或者 \_ 包围的字词会转化成`<em>`标签包围  
*italic* :  一个\*包围  
__blod__ :  两个\_\_包围

###代码

如果要标记一小段行内代码 ，用`` ` `` 反引号包起来  
如果要在代码中插入`` ` ``反引号，则可以用多个反引号包围

###图片

和链接类似的格式  

1. 行内式
        ![Alt text](/path/to/img.jpg "Optional Title")
    详细叙述如下：
    一个惊叹号 !  
    接着一个方括号，里面放上图片的替代文字  
    接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

2. 参考式
        ![Alt text][id]
    `[id]`是图片参考的名称，格式参考链接
        [id]: url/to/image  "Optional title attribute"

##其他

###反斜杠

Markdown 可以利用反斜杠来**插入**一些在语法中有其它意义的**符号**

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
    
    \   反斜线
    `   反引号(代码)
    *   星号(强调，分隔，无序列表)
    _   底线(强调，分隔)
    {}  花括号()
    []  方括号(链接)
    ()  括弧(链接后接的括号)
    #   井字号(标题)
    +   加号(无序列表)
    -   减号(无序列表)
    .   英文句点(有序列表)
    !   惊叹号(图片)

###自动链接

Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用**方括号**包起来

    网址格式：     <http://example.com/>
    邮箱格式：     <address@example.com>

##高级应用

###表格

    表头1  | 表头2
    ------------- | -------------
    Content Cell  | Content Cell
    Content Cell  | Content Cell
    
    | 表头1  | 表头2|
    | ------------- | ------------- |
    | Content Cell  | Content Cell  |
    | Content Cell  | Content Cell  |
    
    | 名字 | 描述          |
    | ------------- | ----------- |
    | Help      | Display the help window.|
    | Close     | Closes a window     |

    表格中也可以使用普通文本的删除线，斜体等效果
    
    | 名字 | 描述          |
    | ------------- | ----------- |
    | Help      | ~~Display the~~ help window.|
    | Close     | _Closes_ a window     |

    表格可以指定对齐方式
    
    | 左对齐 | 居中  | 右对齐 |
    | :------------ |:---------------:| -----:|
    | col 3 is      | some wordy text | $1600 |
    | col 2 is      | centered        |   $12 |
    | zebra stripes | are neat        |    $1 |

