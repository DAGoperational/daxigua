## 合成大西瓜

### 本地启动

1. 安装 serve 工具：

    ```bash
    npm i -g serve
    ```

2. 进入 daxigua 目录，运行 serve：

    ```bash
    serve
    ```
   
3. 打开浏览器访问 localhost:5000 即可！

4. 想要修改只需在 src/project.js 文件中搜索 '// '（斜杠斜杠空格），就能快速找到对应修改位置！

### 魔改原理

游戏的过程是：点击 => 碰撞 => 计分 => 展示

#### 1. 改分数

改分数有两种实现方式，修改计分规则，或者修改最后要展示的分数。原理很简单，搜索分数对应的英文单词 "score" 或者添加分数 "addScore"。

发现分数是由 default.score 作为统计值的，有这么一行代码：

```javascript
a.default.score += this.fruitNumber + 1
```

那我只要把基数 1 改为自己定义的数字即可~ 当然也可以让用户自己输入！

```javascript
a.default.score += this.fruitNumber + extraScore
```

当然，这种方式玩游戏就没有多少意思啦~

#### 2. 改图片

改图片的原理非常简单，直接找到原有的图片，然后用相同名称、相同格式、相同尺寸的图片进行替换即可！

我帮大家整理了图片替换表，地址如下：

【腾讯文档】魔改大西瓜可替换的素材 https://docs.qq.com/sheet/DS0d2VVVJYmpvZ0pZ

还有其他魔改方式，比如每次都下落相同水果，思路就是 "定位代码" => "修改调试"。持续补充！

大家可以学习下作者的源码，真的强！

### 发布上线

1. 使用 Vercel，在网页 index.html 文件所在目录通过一行命令即可自动发布到它提供的服务器并生成可访问的网址，还能和自己的域名绑定！（我的魔改版就是这么发布的）

2. 使用腾讯云静态网站托管服务，下载官方工具，也是一行命令，即可发布至腾讯云服务器！

可以参考这两篇文章的方式部署自己的网站：

腾讯云静态托管：[docsify+云开发，高效创造你的文档网站​](https://mp.weixin.qq.com/s/Noe90mhVssuBcySyb6TTNA)

Vercel：[尝鲜 Svelte 新框架，动手开发读书笔记](https://mp.weixin.qq.com/s/W-TWxOJTr4gSQkCyIquNuA)
