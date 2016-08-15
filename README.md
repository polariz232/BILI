# 2233

- 目前是爬取指定av号的弹幕存到本地。原理是贴吧上看到的2233
- 弹幕信息有内容，时间，和时间2233
- 当初hackPKU的第三天上午撸了2,3小时的个说2233
- 新增网页版 [传送门](http://tmn07.ren/BILI)
- 下个版本可能做一些批量的啥啥

## 说明

### 使用方法

```
------------------------------------------------------
|the Most easy usage is :python bilibili.py av_number|
------------------------------------------------------
and there are some argv to optional
-h, --help: to get this.
-v, --version: to get the version
-o filename, --output filename: to output danmus in filename.txt
-x, --xml: to get filename.xml
```

### 示例
![python bilibili.py 5227685](./res/use.png)


### 网页版
- [传送门](http://tmn07.ren/BILI)
- 防表单的重复提交——token
- 调系统命令。权限等等。。例如读写权限，
- bs4 的 lxml。。魔性。。
- <?[php]  ?> 如果配置没打开短标签可能会.....

![web](./res/web.png)


### 怎么发现的

- 我是贴吧里发现这个的秘密2233
- 刚刚才看到那个包2233![xml](./res/response.png)
- 然后全局找一下这串数字2233![cid](./res/cid.png)

### 压缩的理解

-  request 发送的'Accept-Encoding': 'gzip' 告诉服务器我这里支持这几种压缩的流？然后服务器支持的话会选择一种发。
-  听说 不加这一条会放回原始的数据，但是B站不行
-  response里可能会有。Content-Encoding:gzip 表示发给你的是gzip压缩的。
-  python中用 response.info().get('Content-Encoding')获取
-  视频页面是'gzip'压缩传过来的
-  弹幕xml是'deflate'压缩传过来的

### 版本说明
- 第一个版本，xml是用xml.dom.minidom这个库来解析的，看前三个commit
- 这个版本，cid用这正则来获取，加上了header（然并卵），bs4来解析xml
- 现在又加了命令行参数
- 加了网页版orz.


