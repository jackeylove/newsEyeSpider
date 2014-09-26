newsEyeSpider
=============

抓取各报社报纸信息－采用配置文件形式实现的一个简单的可定制爬虫

#项目说明

>为采集各大报社报刊信息所做的网络爬虫

>考虑到项目的可扩展性采用配置文件形式实现可定制

>用户可依据增添配置文件项来扩展爬虫所抓取的信息

>2014-09-26　当前仅实现获取信息

#配置文件说明

>过滤规则采用了Jsoup的过滤形式

>例如

>>a[id=href]过滤出a标签包含有id属性,并且id属性的值为href

>>div[class]过滤出div标签包含有class属性

>>table过滤出table标签

>'class'标签表示一种解析类型

>>'newspaper'表示一家报刊

>>>‘name‘属性表示报刊名称

>>>’startUrl‘属性表示该报刊的起始页面(注意页面跳转问题，代码实现中已经解决大部分跳转问题)

>>>’encode‘属性表示页面的编码(存在个别网站抓取下来乱码，只要在这里更改编码即可)

>>'rulePage'表示获取版面信息的过滤规则

>>>‘pageEle’标签标识版面信息所包含在的外层标签

>>>>'node'值为true表示所有的版面信息包含在这一个标签下,值为false表示版面信息包含在这一组标签下

>>>'pageEles'标签标识版面信息所在的一组标签

>>>'eleAttr'标签标识版面链接所在标签的哪个属性

>>>>’contains‘属性可指定所得到的版面链接必须包含某个子串 (可缺省)

>>>'subString'标签标识所获取到的字符串需要截取,例: 23,38则将获取字符串的第23位到第38位(可缺省)

>>'ruleSource'标识获取新闻链接的过滤规则

>>>'sourceEle'标签标识新闻链接所包含在的外层标签

>>>'sourceEles'标签标识新闻链接所在的一组标签

>>'ruleTitle'标签标识新闻标题的过滤规则

>>>'titleEle'标签标识新闻标题所包含在的外层标签

>>>'titleEles'标签标识新闻标题所在标签，默认会获取该标签的正文内容

>>'rulePublishDate'标签说明新闻发布时间的组织形式，目前提供４中形式(xxxx-xx/xx、xxxxxxxx、xxxx年xx月xx日、xxxx-xx-xx)

>>>'url'属性说明时间信息是否来自新闻所在页面的url，默认为true,指定位false时必须包含publishEle标签(可缺省)

>>'publishEle'当时间信息并非来自url时我们认为其来源于文章正文,标签正文标识时间所在标签包含在的属性

>>>'ele'属性表示时间所在标签的过滤规则

>>'ruleBody'标签标识新闻正文部分的过滤规则

>>>'bodyEle'标签标识正文部所包含在的外层标签

>>>'bodyEles'标签标识需要提取正文部分的哪种标签，默认会获取这种标签下的所有正文内容

>>>'regex'用于处理获取到的文本中的特殊字符,这里为需要替换的字符/字符串

>>>'replacement'这里为替换后的字符/字符串

>>'ruleImg'标签标识新闻种所包含的图片所在的外层标签，程序会获取其下的所有img标签内容
