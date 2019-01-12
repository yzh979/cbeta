# 大藏经(cbeta)开源阅读计划  (做最好的开源阅藏程序)

因为cbeta是用C++写的，我这里没有正版windows，所以一直是把cbeta光盘中的xml拷贝下来，自己处理之后阅读。
最近cbeta的xml格式发生了变化(从TEI.2格式转为P5格式)。所以重写了我的程序。随便共享出来给有需要的人。

## 主要特点

1. 舒适的阅读体验！主要针对Linux与苹果优化. (Windows暂时显示效果不佳)
2. 正确的显示经文, 修正了很多CBETA上错误的显示
3. 支持简体、繁体、全部(包括扩展F区)的异体字的阅读, 搜索, 查询。不使用URO外的类推简化字
4. 集成多部字典词典，更方便的查询词典/字典
5. 异体字的规范化(基本按照教育部字典, 教育部字典没有的按照大陆简化字和藏经高频取为标准字)
6. 拼音标注, 语音合成，自动朗读
7. 梵文悉曇体完全使用unicode10.0标准显示, 搜索
8. 对计算机友好的完全开放的接口, url支持命令行操作, 支持多种输出形式:xml, json, pdf, html, epub, docx, mp3...
9. 使用UNICODE10.0版本，汉字显示存储支持到扩展F区。统一使用UTF8编码、UNIX文档格式保存全部文本资料


## 哲学或者主旨、版权
1. 这里所指的版权，针对对象是资源。资源的内涵包括这里的代码, 以及其他整理出的, 包括但是不限于css, js, 二次整理的字典, 词典等
2. 佛法是人类文明最珍贵的精华，对东方文化，及人类文明，有深远的影响。是法住法位，非佛作亦非余人作。所以为了传播佛法，禁止商业行为，是十分愚蠢的。
3. 这些代码只是我自己用的，为了自己用的舒服，开放出来也只是基于共享精神，所以如果有需要的功能，可以给我发邮件，如果我感兴趣而且有时间也许会加上
4. 版权问题：这些代码都是完全公开的，没有版权，以后考虑加入MIT或者公共域等其他类似的版权，你可以拿去完全的修改，公开发行，去掉我的名字，融资上市挣钱，这些我都不关心
5. 禁止行为：任何导致作者有可能不能使用自己的资源的行为都是禁止的。我在任何情况下都完全拥有使用自己代码、资源的权力，所有权、著作权，修改权，无论你怎么修改这些资源。
6. 免责声明：因为免费所以免责。如果(因为使用此软件)出了什么事情，都是你自己的事儿，CPU过热烧毁，和老婆吵架了，或者破坏了世界和平，毁灭了宇宙，都跟我一点关系都没有，不要来找我！本人不保障此软件的安全性，不保障软件中没有包含病毒、蠕虫或者其他任何有害程序。
7. 法律保障：你把这些拿去使用不会有任何法律上的烦恼，因为采用的一切技术都是free的技术，不需要你购买开发工具，不需要你购买操作系统，不需要你购买数据库，不需要你购买类似java或者VC++这样由商业公司完全控制的软件
8. 戒律保障：因为全部使用自由软件，所以你可以持最严格的戒律，尤其是盗戒，保持戒律清净，不用担心盗版软件，也不用担心商业公司在你使用一段时间之后修改了软件条款，而你处于闭关状态无法及时响应。这是我唯一可以保障的。
9. 因为这是自由软件，但是不是免费软件，所以此资源完全可以通过商业途径传播，可以倒找钱、白送、高价、天价或者宇宙价出售光盘/U盘/硬盘, 可以随有价光盘/U盘一起赠送！这些不需要本人的任何授权！也不需要通知本人。
10. 庄春江居士的阿含词典已经得到庄春江居士的(非營利用途)授权，但是此词典会持续更新，最新版在 [最新版本](http://agama.buddhason.org) 
11. [威廉梵英词典](https://github.com/sanskrit-lexicon/Cologne-Sanskrit-Tamil), from http://www.sanskrit-lexicon.uni-koeln.de/
12. [觉悟之路](http://dhamma.sutta.org/pali-course/Pali-Chinese-English%20Dictionary.html) 提供的15部巴利语词典: pali-hant.json.gz

## 与cbeta阅读器的差异
1. 快如闪电! 稳如磐石!
2. 全面支持unicode 10.0. 使用unicode显示悉昙字(目前只替换了部分悉曇字). 使用: https://en.wikipedia.org/wiki/Siddha%E1%B9%83_script
3. 使用unicode显示异体字，尽可能的使用接近藏经原貌的字; 不使用兼容字
4. 支持简体阅读和简体搜索, 支持转换异体字为正字
5. 集成多部字典词典，划词查询, 方便易用; 使用Levenshtein算法查询词典
6. 标点符号破折号替换为单一字符，不会断开。
7. 使用python和xslt编写，可以运行在目前几乎所有主流操作系统中: 从meego到AIX。
8. cbeta在注释问题字段的时候使用两个anchor标签夹在一起的做法。导致获得这些字段非常困难, 考虑替换成orig标签，以便自由切换不同藏经
9. 使用byline cb:type="Author"表示作者, byline cb:type="translator"表示译者，混用大小写和中英文，还同时使用cb:jl_byline，含义模糊
10. p rend="inline" 的写法，本来就是一个行内元素,导致T55n2157_024.xml显示不正常
11. cbeta的note标注有时候显示的是勘误后的文字，有时候显示的是勘误前的文字。让人迷惑
12. 无上士调御丈夫 中间的标点去掉


## 技术方式和预期效果

1. 速度.目前来看相比CBETA速度快上很多。完全不消耗服务器资源。对浏览器的消耗也非常小。速度非常快。CBETA在多处有卡顿的现象。原因不明，阅读体验不佳
目前唯一发现有些微卡顿的是' 胎藏梵字真言上卷', (T18/T18n0854_001.xml),用时0.5秒降为0.09秒，原因是使用了太多的图片和文件比较大所导致;优化速度后最大(2.7M)的文件'朝鮮佛教通史'(B31n0170_003.xml)由0.9秒降低为0.45秒，
原来速度最慢的K35n1257_025由2.5秒降为0.25秒,已经可用
2. 代码非常少。修改部署容易
4. 自制的悉昙字字体已经正常, 使用Unicode10.0的码表来显现, ttf文件只有9k大小
5. 部分Ｆ区汉字使用了webfont技术，不需要安装字库即可正常显示(没有覆盖全部用到的Ｆ区汉字, 所以还是需要安装大字库)
6. 整体程序非常简单。只有一个tei.xsl文件和一个tei.css文件作为显示效果。而阅读效果比较好。修改简单方便，适合长期阅读藏经使用。


## 技术方式

1. 使用xslt来处理xml, 然后使用在xml中直接嵌入xslt的方式, 就可以直接在浏览器中阅读了。
如果希望自己使用的人, 可以自己搭建一个nginx服务器。将静态文件指向xml和tei.xsl,tei.css文件所在目录即可; 甚至只需要把xml文件, tei.xsl和tei.css文件放在一起即可使用

2. 使用python来处理其他事情, 主要是生成目录, 搜索

3. 尽量少的使用js控制， 尽量少的使用数据库, 前端生成内容, 对搜索引擎友好, 对爬虫友好

4. 在线直接阅读xml文件. 不单独生成html，占用空间小。 pdf格式文件使用xsl-fo方式直接在线生成


## 安装说明

1. 示例是在ubuntu16.04上所做。其他操作系统仿照即可。不需要安装数据库，web服务器，只需要安装python即可
2. 假设安装到$HOME/cbeta目录
3. 安装python虚拟环境, 会生成一个py36的目录，里面是python的可执行程序(需要python3.6及以上版本)
```
 $ git clone https://github.com/zhaowenping/cbeta.git
 $ cd cbeta
 $ python3 -m venv py36
 $ cd py36
 $ . bin/activate
 $ cd ..
 $ pip install --upgrade pip
 $ pip install -r requirements.txt
 ```
4. 将全部的xml文件移动到 cbeta/xml目录中,原有目录保留, 需要使用make_xml.py文件生成, 主要作用是两个，第一，去掉xml文件中的默认地址空间，第二，添加tei.xsl文件的链接上去
5. 运行程序 $ python reader.py
6. 打开浏览器，默认地址 http://localhost:8081 即可看到

## 使用说明

1. 系统支持部分restful接口。
2. 在阅读中查询某字或者某词，使用鼠标选中希望查询的字词，然后把鼠标悬浮到被选择的字词上，如果在字典中存在被查询的字词，就会自动悬浮显示
3. 单独使用字典词典，例如查询'仁'字, 可以在浏览器中输入 http://localhost:8081/dict/仁
4. 查詢指定字典词典，例如在丁福保詞典中查询'佛陀'一詞, 可以在浏览器中输入 http://localhost:8081/dict/dfb/佛陀 , 目前可以查詢的有fk,kangxi,ccc,fxcd,dfb
5. 支持dict协议(rfc2229), 使用 $ apt install dict 安装dict客户端。使用$ dict 佛陀 -h kepan.org 即可查询字典

## 文件列表
1. static/tei.xsl 主体程序
2. static/taisho.xsl 大正藏转换程序
3. static/siddham.ttf 符合unicode10.0的悉昙体字库
4. static/siddham.sfd 符合unicode10.0的悉昙体字库的fontforg文件，可以根据这个文件继续修改字库
5. static/siddham.woff 符合unicode10.0的悉昙体字库,可以通过webfont方式使用悉昙体字库，以便读者不用安装字库即可阅读悉昙体
6. terms.txt  佛教词汇大全，目前搜集了不到8万词汇，用来给藏经分词用的, 以便全文检索使用
7. w_normal.txt 制作的组合字表, 用来清洗xml文档
8. yoga 目录,打算后期为瑜伽师地论做现代化标点
9. reader.py python的web程序入口, 提供目录、搜索等服务
10.  .lst文件 tab分割的目录文件
11. temp目录, 页面的jinja2模板文件
12. fo目录, 使用fop程序生成pdf的程序，使用的时候需要修改fop.xconf文件中的directory标签，指向字库文件目录(fop2.1)
13. cb-Siddam.woff 原cbeta的悉檀字庫，因爲不標準所以轉換而成
14. dictd.py 文件: 支持[dict协议](https://tools.ietf.org/html/rfc2229) 的字典查询服务器程序


## 字库

1. 页面整体上是使用冬青黑体或者苹方字体显示主要文字，使用SimSun显示标点符号，你可以随意修改为自己喜欢的字体
2. 建议下载花園明朝(HanaMin)字体以便显示生僻字  http://fonts.jp/hanazono/ 或者 http://ctext.org/font-test-page/zh, 因为花园字体是自由字体，尤其是花園明朝B一定要安装
3. 安装天城体字体命令: sudo apt install fonts-deva

## 词典

在转码过程中的错误使用U+FFFD替换，需要进一步的校对原文；法相词典下都需要进一步校堪工作

|序号| 词典                           | 文件名                       |  词条数量|  注释      | 
|----| -------------------------------|:----------------------------:| --------:|----------- | 
|    | 庄春江汉译阿含经词典ver4       | ccc.json                     |   4573   |            |
|    | 佛學常見詞彙（陳義孝）         | cxy.json                     |   5858   |            |
|    | 丁福保《佛學大辭典》           | dfb.json.gz                  |  31366   |            |
|    | 佛光大辞典                     | fk.json.gz                   |  24445   |            |
|    | 康熙字典                       | kangxi.json.gz               |  28193   |            |
|    | 《南山律學辭典》               | nvd.json                     |   6025   |            |
|    | 威廉梵英词典                   | sa-en.json.gz                | 160625   |            |
|    | 15部巴利语词典                 | pali-hant.json.gz            |  49111   |            |
|    | 三藏法数                       | szfs.json                    |   1405   |已校对      |
|    | Yates梵英词典                  | yat.json.gz                  |  44720   |            |
|    | 于凌波唯识名词白话新解         | ylb.json                     |   1506   |            |
|    | 朱芾煌《法相辭典》             | fxcd.json.gz                 |  14687   |            | 
|    | 宋普潤法雲《翻譯名義集》       | fymyj.json.gz                |   1085   |            |
|    | 宋，普濟《五燈會元》           | wdhy.json.gz                 |   2045   |            |
|    | 《歷代名僧辭典》顧偉康編       | ldms.json.gz                 |   2121   |            |
|    | 俗語佛源                       | syfy.json.gz                 |    566   |            |
|    | 閱藏知津,明蕅益智旭撰顧偉康編輯| yzzj.json.gz                 |   1701   |            |
|    | 《中华佛教百科全书》蓝吉富主编 | bkqs.json.gz                 |   6331   |  简体      |

## 浏览器兼容性
1. 主流浏览器: firefox、opera、chrome、safari、搜狗浏览器、IOS手机等主流浏览器都没有发现任何问题
2. 360浏览器在调整兼容性之后可以正常使用了。但是有些地方渲染比较奇怪
3. 微软系浏览器: Edge 12、ie11也可以翻页了，一切正常, 只是显示效果不理想
4. ie6已经确定无法使用, 不必尝试了; ie7没有测试过, 估计没戏; ie8已经可以使用了，只是导航条有些显示问题
5. 因为导航需要探测文件存在与否，所以可能出现文件不存在的警告是正常的
6. 所有浏览器都只能使用xslt1.0版本语法,其中ie更有一些限制
7. firefox对勘误注释无法渲染为红色(anchor标签的问题); 也无法正常显示部分异体字, 会显示为对应的XML实体

| 浏览器        | 渲染引擎      | xslt版本| 
| ------------- |:-------------:| -------:| 
| 360           | Microsoft     |  1      |
| ie8           | Microsoft     |  1      |
| Edge          | Microsoft     |  1      |
| firefox       | Transformiix  |  1.0    |
| chrome        | libxslt       |  1.0    |
| opera         | libxslt       |  1.0    |
| safari(ios)   | libxslt       |  1.0    |
| safari(pc)    | libxslt       |  1.0    |
| 搜狗          | libxslt       |  1.0    |
| midori        | libxslt       |  1.0    |
| links2        |               |         |
| w3m           |               |         |
| lynx          |               |         |


## TODO
- [x] 翻页, 上一页，下一页，经内分页功能, 转make_xml程序处理
- [x] 全文搜索 (使用es实现了一版)
    - [x] 全文字搜索
    - [ ] 全文词搜索
    - [ ] 全文搜索的查询语法
    - [ ] 悉昙体的全文搜索, 使用拉丁字母搜索
- [ ] 删除悉昙字的图片，使用Unicode10.0的字来显现。目前字体做了一半  DONE!
- [ ] 删除蘭扎字的图片，暂时设想使用悉昙字的变体来实现
- [x] 对悉昙体叠辅音的支持, 由字库支持，暂时不做处理
- [ ] 登录用户
    - [ ] 对登录用户保存书签
    - [ ] 登录用户自定义xsl, css
    - [ ] 智能书签, 恢复上次阅读处: 每到新的段落就自动保存一次书签，以便保存书签的时候可以细化到段落
- [x] cb:tt标签X23n0438_004.xml应该显示全部汉字，然后显示一行悉曇字.有make_xml程序处理
- [ ] 回到顶部和回到底部的功能，在滚轮向上快速滚动时候出现向上箭头, 向下快速滚动时出现向下箭头，可以点击以便直接回到顶部或者回到底部
- [ ] 查字典词典的时候会和左边的超链接或者染色混淆 FIXME
- [ ] 导出pdf,docx,otf,html,epub,txt等多种格式文档
- [ ] 在点击简字进行简体转换的时候，停留在当前所浏览位置
- [ ] 对终端浏览器的支持
- [ ] 大藏经目录部文件的导航, 完成了一半

## BUG-FIX
2. 翻页需要去检测文件是否存在。如果文件不存在IE会停止处理xml文件，其他浏览器则简单的在控制台打印一条警告
3. 浏览器只能使用xslt1.0版本, 无法做到跨文件目录跳转(没有base-uri() and document-uri()),解决方法: 在自生成的xml中，在cb:mulu中添加一个属性，内容为当前文件名
4. 在注释附近的字在查询字典的时候，会和注释链接到一起，导致显示不正常
5. 跨文件目录无法合并目录树，每个文件都单独显示目录树
6. firefox表格错位: B35n0194_001.xml
7. 佛光山词典多条解释的时候缺失解释
8. midori浏览器在p标签的内容换行时产生一个空格。应该在转换时候去掉回车
9. midori浏览器不支持CJK合字(暂时不需要此功能)
10. 所有浏览器都不支持200d合字. 终端支持

## 汉语拼音使用方式

1. 在方格內輸入漢語拼音並以數字 (1-4) 表示聲調，如：hua2。 （5 代表輕聲）
2. 可以「貼上」整段拼音，如：Pu3tong1hua4 Xue2xi2 Wang3。
3. 如要顯示 ü，請輸入 v5；如果要顯示 nǚ，請輸入 nv3。
4. 如要顯示 ê，請輸入 ea5。

## DEMO

1. 可以在 [美國DEMO1](http://45.76.171.153:8000) 看到演示效果 (目前只有大正藏的两个目录可以点击)
2. 可以在 [中國DEMO2](http://cbeta.kepan.org) 看到演示效果 (目前只有大正藏的两个目录可以点击)

# 全文搜索使用的语法
1. 关键字是AND、OR、NOT。搜索域是title、author、content 可以随意组合,使用()
2. 例如搜索阿含经中的一段话,使用如下语句:  比丘集讲堂 AND title:阿含经

##  感谢

本程序编写过程中得到了如下机构和个人的支持和赞助，表示感谢！

1. cbeta
2. 

##  捐助记录

2018-08-21 22:23:00 收到Starful Night师兄6.88元 用于悉昙体字体开发


##  联系方式 

1. 可以通过wenping_zhao@126.com与我联系使用中的问题, 提交BUG

2. 欢迎加入此项目!

