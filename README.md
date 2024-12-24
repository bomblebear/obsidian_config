# **1. CSS样式设置**
Obsidian中提供了非常多的主题，但是作为强迫整患者，最合适的肯定是自己瞎搞出来的。

Obsidian中渲染包含两种格式，编辑模式使用 CodeMirror 编辑器，而阅读模式则使用渲染后的 Markdown 预览。所以要注意区分一下，这两者对应的元素名称并不相同

按 `Ctrl + Shift + I` ，打开开发者工具，点击窗口左上角的**选择网页中的相应元素即可进行检查**，回到 Obsidian 的窗口，此时鼠标移动至任何地方都会有高亮突出显示。

然后戳对应的元素，就能看到对应的elements的配置信息了，照这个葫芦来画，然后将保存的css文件放置在 `.obsidian/snippets/` 内，然后在设置中启用CSS代码片段即可

+ 字体套用思源黑体 `Source Han Sans CN VF` 
+ 代码字体(mono)使用 `Ubuntu Mono` 

#### 一个例子**obsidian.css**
```css
/* obsidian.css */

/* 定义图片居中 */
img {
        display: block !important;
        margin-left: auto !important;
        margin-right: auto !important;
}
    
 .markdown-source-view.mod-cm6 .cm-content > * {
        margin: auto auto !important;
}


/* 定义行内代码的颜色 */
.cm-s-obsidian span.cm-inline-code
{
    color: purple;   
    font-size: 0.95em; /* 相对于父元素的字体大小 */
}


/* 定义加粗字体颜色 */
.cm-strong, b, strong{
  color: #3498db; /* 这里是深蓝色的示例 */
  font-weight: 800;
}

/* 定义斜体颜色 */
.cm-em, i, em {
    color: #3498db; /* 这里是深蓝色的示例 */
}


/* 下面是1234级标题 */

.HyperMD-header-1, .inline-title[data-level='1'], .HyperMD-list-line .cm-header-1 {

    color:  ;
    line-height: 2.7; /* 行间距为2倍 */
    font-weight: 540

}

.HyperMD-header-2, .inline-title[data-level='2'], .HyperMD-list-line .cm-header-2 {

    color: ;
    line-height: 2.3; /* 行间距为1.7倍 */
    font-weight: 540

}

.HyperMD-header-3, .inline-title[data-level='3'], .HyperMD-list-line .cm-header-3 {

    color: ;
    line-height: 2.0; /* 行间距为1.5倍 */
    font-weight: 530

}

.HyperMD-header-4, .inline-title[data-level='4'], .HyperMD-list-line .cm-header-4 {

    color: ;
    line-height: 1.9; /* 行间距为1.5倍 */
    font-weight: 530

}



/* 强调的字体 ==这是强调字体==，17px */

.cm-s-obsidian span.cm-formatting-highlight, .cm-s-obsidian span.cm-highlight, .markdown-rendered mark
{
    background-color: ;
    color: ;
    line-height: 2.2; /* 行间距为2倍 */
    font-size: 1.25em; /* 相对于父元素的字体大小 */
    font-weight: bold; /* 加粗 */
}


/* 调整正文行间距 */
.markdown-source-view.mod-cm6.is-readable-line-width .cm-line,
.markdown-rendered p
{
    line-height: 1.6; /* 行间距为1.5倍 */
}


/* 给超链接格式添加一个背景色 */
.markdown-source-view.mod-cm6 .cm-link .cm-underline,
.markdown-source-view.mod-cm6 .cm-url .cm-underline, .external-link {
    background-color: #f2f2f2; /* 淡灰色的背景色 */
    padding: ; /* 可以根据需要添加内边距 2px */
}



/* 引用文字减小大小 */
.cm-s-obsidian span.cm-quote.cm-quote-1
{
    font-size: 0.85em; /* 相对于父元素的字体大小 */
}


/* 角注颜色 */
.cm-s-obsidian span.cm-footref
{

    color:purple;

}

```


# **2. Obsidian Plugins**
==需要的插件/逐渐更新中...==
### 2.1 😆Emoji Toolbar

`Ctrl + P + emoji`触发
因为原来在notion用习惯了，喜欢在标题里加一些类似🚧✅的emoji

### 2.2 📁Consistent Attachments and Links

+ 为了保证markdown文件的可移植性，我选择了在每个目录下建一个附件文件夹（如下图的设置），用于存储大量的图片等附件，但是这样会出现一个问题，万一我想移动md文件的位置，这些附件怎么办？
+ 此插件就可以顺带将附件也一起对应转移的工具；

	- `Default location for new attachments: In subfolder under current folder`
	- `Subfolder name: attachments`

==Replace All Wiki Links with Markdown Links==
Obsidian的wikilink虽然好用简单，但是不具备通用性，但是完全的关闭的话，就不能用markdown格式链接到固定的段落了，所以我是把这个选项开着，然后使用如下命令进行转换：
`Consistent Attachments and Links: Replace All Wiki Links with Markdown Links`
==Convert All Link Paths to Relative==
Obsdian的文件索引完全不需要相对路径（无论是wikilink还是markdown原生的link），虽然在软件内没什么问题，但是如果移植就会不知道文件在哪里了
### 2.3 📁Clear Unused Images
+ `Clear Unused Images and Attachments`
markdown引用的图片和文件，如果你把md文件删除，附件其实还没有删除掉；
本着强迫症的原则，必须解决😡
### 2.4 🖼️Local Image Plus
用于从网页复制粘贴文件时，可以自动下载贴图到对应的附件文件夹。
否则直接复制可能就会出现图片无法解析的现象
### 2.5 🖼️Paste image rename
直接复制剪贴板的图片进Obsidian的笔记里，命名的方式全是 `paste***`+一堆数字，该插件可以自动或者手动修改名称；
`auto rename`
### 2.6 🖼️Mousewheel Image Zoom
原生的markdown修改图片大小太麻烦了，需要手动修改高度长度信息
此插件可以通过快捷键 `alt + +/-`完成大小修改
==💡那有同学就要问了，怎么居中呢？==
同样，原生的markdown修改居中的办法这里居然用不了，麻烦的方式是使用html的标记语言，但是这也太逆天了，慢到死，手打一堆什么 `align = center`啥啥啥的，最直接的办法去Obsidian设置里修改CSS样式，来直接改变显示设置，把下面的代码存成`.css`格式放在`Obsidian\.obsidian\snippets`路径下，再在设置里面启用即可（**这里的代码一并放置在了前面的css样式中了，不需要另外再弄了**）

```css
img {
        display: block !important;
        margin-left: auto !important;
        margin-right: auto !important;
}
    
 .markdown-source-view.mod-cm6 .cm-content > * {
        margin: auto auto !important;
}
```



### 2.7 💡Dataview & DB Folder
>[blacksmithgu/obsidian-dataview: A data index and query language over Markdown files, for https://obsidian.md/.](https://github.com/blacksmithgu/obsidian-dataview)

因为抛弃notion，导致失去了非常好用的database功能TT
- https://bubblebear.notion.site/
用Dataview & DB Folder进行补偿方案，但是这个数据库列表有点丑，所以暂时先不用，后面再说吧.

简单语法例如：
 + 今天是  **`=dateformat(date(today)," yyyy 年 M 月 d 日")`** 
 + 距离2025年除夕还有 **`= round((date(2025-01-28) - date(now)).days)`** 天
配合callout
> [!abstract] 
> - 今天是  **`=dateformat(date(today)," yyyy 年 M 月 d 日")`** 
> - 距离2025年除夕还有 **`= round((date(2025-01-28) - date(now)).days)`** 天

---

这次搬迁发现之前在notion搞得很多的笔记界面，其实是因为我想把notion当成一个全面的网盘，由于后面发现了同济的校友邮箱自带的OneDrive，就取消了这个打算，使用Obsidian也算是把文件全都交由OneDrive同步了（失去了手机端即时预览的优势/yuque和notion的app可以做到）
并且还发现之前很多笔记非常的捞，都不想同步了，都跟天书一样，自己都看不懂。

+ 对于私人文件来说，网页共享什么的其实无关痛痒
+ 如果需要团队协作，或者各系统联动，还是notion和yuque方便
+ 但是我再也不会把后面产生的大宗的笔记和文件放置在这二者上面了
+ Obsidian内部尽量保证各个md文件的独立性，这样可迁移性就非常的高
+ 本地的流畅性还是好啊


### 2.8 💡Advanced Tables
这个插件用于生成markdown表格，表格确实比较难搞，`|` + `tab`

| name | age |
| ---- | --- |
| me   | 18  |
|      |     |

也可以在 `Ctrl + P`在命令面板操作

### 2.9 🎨Excalidraw
[zsviczian/obsidian-excalidraw-plugin: A plugin to edit and view Excalidraw drawings in Obsidian](https://github.com/zsviczian/obsidian-excalidraw-plugin)
- 这个插件做的很棒！对我而言，我只需要能够方便快捷的画出一些逻辑框图，如果希望认真画的话还是得去visio

1. 我把`Excalidraw: Cearte new drawing - IN A NEW TAB - and embed into active document`加到了命令窗口的`pin`里面，方便插入绘图；
2. 因为他的绘图文件格式是`md`文件，这样会造成一个问题，导致`clear unused image`无法对其完成清理，目前我不知道怎么解决；
3. 正是因为上面这个问题，所以为了便于清理，我没办法把这个绘图文件放在对应`md`文件的`attachments`文件夹中（违背了我的原则😭），把`Basic`设置中的，`Use Excalidraw folder when embedding ...`打开了，放在了一个统一的根目录下的文件夹内；


# **3. Markdown**
+ [MarkDown语法 超详细教程 - 经验分享 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/435)

大部分其实我都知道了，把之前不熟悉的列举一下：

+ 文本加粗：`ctrl + B`
+ 文本斜体：`ctrl + I`
+ **~~这是文本删除线~~**
```
~~这是一段加了删除线的文本~~
```

+ <u> 这是文本下划线</u>
```
<u>这是一段加了下划线的文本</u>
```

+ 文本引用：`>`

+ **表格比较复杂，请用Advanced Tables 插件**

- [x] 这是啥 
- [ ] 干完了
```
- [ ] 待办任务列表1 
- [ ] 待办任务列表2 
- [x] 已办任务列表1 <!-- 英文字母X --> 
- [x] 已办任务列表2
```

+ **原来markdown还有注释**
<!-- 这里是注释的内容 -->

+ 对文本插入超链接 `ctrl + k`

+ 转义字符，前面加 `\`

+ **嵌入音频**
```
<audio controls="controls" preload="none" src="https://www.ldoceonline.com/media/english/exaProns/p008-001803372.mp3?version=1.2.30"></audio>
```
<audio controls="controls" preload="none" src="https://www.ldoceonline.com/media/english/exaProns/p008-001803372.mp3?version=1.2.30"></audio>

+ **嵌入视频**
```
<video width="600" height="420" controls> 
	<source src="movie.mp4" type="video/mp4"> 
	<source src="movie.ogg" type="video/ogg"> 
	<source src="movie.webm" type="video/webm"> 
</video>
```
- **Video标签** 支持的视频格式 ：`mp4`, `ogg`, `webm`


+ **脚注`[^3]`**
H脚注的用法很简单[^1]  ，只需要在段落中需要插[^其实可以这么做]入脚注的地方标注一个符号，再在段落后对这个符号进行解释即可。 [^1] 比如这是一个简单的脚注，[^1] 这是一个长一些的脚注。[^长脚注] 

[^1]: 这是脚注的内容。
[^长脚注]:不在乎你的注释是什么，阅读模式下会自动编号

# **4. Obsidian 功能**
> [!Title] 使用原则
> + 为了保证可迁移性，尽量去使用原生的Markdown语法；
> + 尽量避免使用wikilink等Obsidian特有语法；
> + 使用`Consistent Attachments and Links: Replace All Wiki Links with Markdown Links`进行转换；
> + 这个callout模块就不是原生语法；
+ [由此开始 - Obsidian 中文帮助 - Obsidian Publish](https://publish.obsidian.md/help-zh/%E7%94%B1%E6%AD%A4%E5%BC%80%E5%A7%8B)

==Command Palette==
`Ctrl + P`
==双链笔记&Tag==
```
链接到某一篇笔记：[[ ]]

链接到某一篇笔记中的某个标题：[[ # ]]

链接到某一篇笔记中的某个段落（块）：[[ # ^ ]]

为链接创建定义（关键词）：[[ | 关键词]]

链接到外部文件如印象笔记：[关键词]（链接）
```

~~尽量去使用markdown原生的链接格式！在设置中将 `use [[wikilinks]]` 关闭~~
如果关闭就不能方便的链接到段落，只能连接到文章了，所以还是开着吧，**最后可以通过插件全部改正**：
+ [2.2 📁Consistent Attachments and Links](#2.2%20📁Consistent%20Attachments%20and%20Links) 

==Tag功能==

#Obsidian
这样，就能检索所有出现这个关键词的文件了

==Quick Switcher==

`Ctrl + O`即可快速切换笔记

==最近发现这个callout非常的好看==
[Callouts - Obsidian Help](https://help.obsidian.md/Editing+and+formatting/Callouts#Supported+types)

>[!info] info

>[!example] example

>[!bug] bug


# **5. 如何移植所有配置**
[bomblebear/obsidian_config](https://github.com/bomblebear/obsidian_config)

1. 只需要将`.obsidian`文件夹整个复制到新的仓库即可，里面会包含所有已经设置好插件及配置；
2. 由于我使用了自己的字体配置，所以加入了一个`font`文件夹，将字体文件安装到本地即可删除；不希望使用该字体的可以分别改成**微软雅黑**和**consolas**；
3. 设置中开启`commutiy plugins`
4. 为了可以使用`ctrl`+鼠标滚轮进行缩放，设置中`appearance`打开`quick font size adjustment`



