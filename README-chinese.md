机器学习&数据挖掘实战
=====================

##目录

 - [相似图像判别](#user-content-Learn-to-identify-similar-images)
 - [BetaMeow](#user-content-betameow)
 - [豆瓣电影](#user-content-doubanmovie)


##具体内容 


<h3 id="Learn-to-identify-similar-images">相似图片识别</h3>

参考论文后，利用```python3.4```，```Pillow```,```OpenCV```利用平均哈希算法，
感知哈希算法(离散余弦变换)等算法，实现**相似图片识别**。

结合```OpenCV```提供的```Heer```模型实现**人脸的定位和识别。**

该项目是本人的另外一个Repository,感兴趣的话可以在以下给出地址找到

> [Learn-to-identify-similar-images](https://github.com/MashiMaroLjc/Learn-to-identify-similar-images)

更多的文字描述可以在我在Segmentfault的专栏上看到。

> [识别相似图片(一)](https://segmentfault.com/a/1190000004467183)</br>
> [识别相似图片(二)](https://segmentfault.com/a/1190000004500523?_ea=630748)


-----


<h3 id="betameow">BetaMeow</h3>

BetaMeow(五子棋AI)是我在AlphaGo大战李世石后一时兴起弄出来的，经过几次版本的迭代，当前版本有别于传统的五子棋ai。
传统的五子棋采用了搜索算法实现，而**BetaMeow是采用决策树算法实现**，通过人工提供数据，可以进行学习。
虽然现在还有很多不足的地方，但我会慢慢维护和更新。

####如何和BetaMeow一起玩耍

下载BetaMeow相应代码，切换到对应目录，输入以下命令。

```
python ai.py
```

打开浏览器，输入```http://localhost/five```来和BetaMeow一起欢快的玩耍吧。

**注意**，请确保你的**80端口没有被占用**，否则需要你手动修改代码。

####Request

- python >= 3.4 
- flask 0.10.1


-----

<h3 id="doubanmovie">豆瓣电影</h3>

 -  ```spider.py``` + ```douban.py```是利用```requests```模块写的网络爬虫，能够爬取豆瓣的电影和电视剧等信息，**爬取
的信息存储为JSON格式，存储目录可自由指定**，数据包括：
  
  - 电影题目
  - 电影时长
  - 电影类型
  - 电影导演
  - 电影主演
  - 电影地区
  - 电影评分
  - 2-3条电影短评

  你可以指定爬取数据的数目，默认情况下，为无限爬取。即直到存储豆瓣URL的任务队列为空，该爬虫才停止。**支持
断点爬取**，默认情况下```info.txt```会动态记录**已经访问过URL和任务队列，已爬取数量**等信息，当你中断
后，下次再启动```spider.py```，它将会重新读取```info.txt```的信息，**因此请不要随便改动```info.txt```里面的内容。**

 - ```datas.py```分析电影数据的脚本。目前能分析出以下关系：
   - 演员和时长的关系
   - 烂片和好片最多的前五名演员(烂片好片的标准可以通过修改代码改变)
   - 电影地区和时长的关系
   - 导演和电影时长的关系
   - 烂片和好片最多的前五名地区
   - 烂片和好片最多的前五名导演
   - 烂片和好片最多的前五种类型
   - 时长和评分关系
   - 各类型中，片子数量最大(不分好坏)前5名的演员。


- DouBanMovie/data
  
  该目录下是随机挑选的500分数据。

- DouBanMovie/result

  该目录下```datas.py```的分析结果，```jpg```格式


- recommend.py

  实现一个简单的推荐的推荐算法，其根据用户在一段时间内对商品某些标签喜爱程度来推荐商品。
适合少用户/个人使用，代码简单清晰易读。


- api.py

  利用```flask```框架，结合```recommend.py```做得一个```WEB API```,你可以做到以事情
   
   - /recommend/get 

   获取json格式的电影推荐信息

   - /recommend/put?moviename=anyname&comment=good 

   提供电影名字或评分```good```/```bad```来使推荐系统学习，更新模型。

####Request
 - python >= 3.4
 - requests  2.8.1

##To Do List

- [x] 相似图片判别
- [x] 五子棋
- [ ] 根据你在新浪微博上的动态情绪推荐音乐
- [x] 某网站电影信息分析
- [x] 基于上一点，做一个私人电影推荐系统
- [ ] 自己的爬虫包，封装爬取各大网站的爬虫
- [ ] 自己的机器学习算法包

未完待续……


##其他的碎碎语

该Repository是记录我学习**机器学习**`或**数据挖掘**方面的实践记录，由于考虑到文件体积的关系，**如若
涉及大数据文件，我并不会开源全部内容，但会提供部分样例数据。**同时，**如果你对这方面有兴趣，并且有项目
开源在github或者其他地方，欢迎向我推荐你项目的URL，我会在我的README文件上给出友情链接**。当然，你也得**在
你的主页上给出本项目的友情链接**。

如果你对这个Repository有任何的疑问或者建议，可以在issue上告诉我，如果有更好的算法实现，也可PR
给我。

没神马特别情况的话，我会持续更新这个Repository很长一段时间，**欢迎保持Watch或给star支持**，谢谢哒。

##开源协议
Apache License 2.0

##联系我

Twitter [@fatfatrabbit](https://twitter.com/fat_fat_Rabbit)
Edit By [MaHua](http://mahua.jser.me)