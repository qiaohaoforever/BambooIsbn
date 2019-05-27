# DoubanBook
豆瓣读书，自用书籍📚信息查询API

> 最近学习微信小程序，做一个类似“书库”的小demo，大致流程使用摄像头获取书本后面的isbn，通过豆瓣读书API得到书本介绍、豆瓣评分、图书评论等信息，然鹅~~https://api.douban.com/v2/book/isbn/:name~~停服了！

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190508221450746-768961205.png)

在网上找了一圈，有意思了，ISBN——国际标准书号（International Standard Book Number)这种理论上应该公开的信息却没有相关资源！

号称[中国ISBN中心 - 中国版本图书馆](https://www.capub.cn/shtmsl/index_shtmsl.shtml)，这个网站翻了一遍也没有能够查isbn的地方，不可思议！

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190508214142831-1933000597.png)

然后，`鹅厂`是这样的：

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190508164214454-1336103024.png)

`福厂`是这样的:

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190508214755742-733865399.png)

其他厂是这样的：

![image-20190508215025648](/Users/mac/Library/Application Support/typora-user-images/image-20190508215025648.png)


评论看起来也不太靠谱！图书库信息缺失严重，接口调用失败，调用次数计费不清。。。

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190508214905247-1288803417.png)



----



### 豆瓣图书API不在的日子，想ta!

豆瓣提供图书查询API的时候，一个接口就可以查询到书本基本信息、用户评分、用户评论等，豆瓣评分很大程度上描述了一本书受欢迎的程度。但是，近年大家的代码学习也有很多直接调用豆瓣API，~~我也是~~，基于豆瓣数据出现了很多商业app，最近比较火的`多抓鱼`图书评分等数据的来源应该是豆瓣。所以，豆瓣可能也是基于这些原因关闭了图书isbn查询接口。豆瓣关闭图书查询接口后，各个与数据相关的厂商也趁机出来圈钱，质量良莠不齐，豆瓣图书API不在的日子，想ta!



### 自己造！

## ISBN图书查询

调用地址：https://isbn.qiaohaoforever.cn/ISBN

请求方式：GET

返回类型：JSON

请求示例：https://isbn.qiaohaoforever.cn/9787506380263

#### 请求参数（Query）

| 名称 | 类型   | 是否必须 | 描述          |
| ---- | ------ | -------- | ------------- |
| ISBN | STRING | 必选     | 10-13位ISBN码 |

#### 返回参数

| 首级标签 | 名称        | 类型   | 示例值                                                       | 描述             |
| -------- | ----------- | ------ | ------------------------------------------------------------ | ---------------- |
|          | create_time |        | 1557302752213                                                | 初次查询时间戳   |
| comments | rate        | string | 5                                                            | 单个豆瓣用户评分 |
| comments | user        | string | 小莉啊                                                       | 豆瓣用户昵称     |
| comments | img         | string | https://img1.doubanio.com/icon/u47055426-37.jpg              | 豆瓣用户头像     |
| comments | date        | string | 2016-09-27                                                   | 评论发布时间     |
| comments | content     | string | 太宰治唯恐一生过得不失格                                     | 评论内容         |
| tags     | title       | string | 日本文学                                                     | 标签🏷️            |
|          | author      | string | 太宰治                                                       | 图书作者         |
|          | publisher   | string | 作家出版社                                                   | 图书出版社       |
|          | price       | string | 25.00元                                                      | 图书价格         |
|          | isbn        | string | 9787506380263                                                | 图书isbn编号     |
|          | image       | string | https://img1.doubanio.com/view/subject/l/public/s29118837.jpg | 图书封面图片     |
|          | rate        | float  | 8.2                                                          | 图书总评分       |
|          | alt         | string | https://book.douban.com/subject/26647769/                    | 该图书豆瓣页面   |
|          | title       | string | 人间失格                                                     | 书名             |
|          | summary     | string | \n    收录《人间失格》《维庸之妻》《Good-bye》《灯笼》《满愿》《美男子与香烟》《皮肤与心》《蟋蟀》《樱桃》 | 图书简介         |

#### 正常返回结果示例

```json
{
  "create_time": 1557302752213,
  "comments": [
    {
      "rate": "5",
      "user": "小莉啊",
      "img": "https://img1.doubanio.com/icon/u47055426-37.jpg",
      "date": "2016-09-27",
      "content": "太宰治唯恐一生过得不失格"
    },
    {
      "rate": "4",
      "user": "3乐",
      "img": "https://img3.doubanio.com/icon/u2394018-4.jpg",
      "date": "2016-01-29",
      "content": "人间失格这一篇读了很久，很难。不太了解作者所以也无法了解这篇里的不堪。后面的短篇很精彩，goodbye的戛然而止真是令人扼腕。要重读。"
    },
    {
      "rate": "5",
      "user": "小丑向月亮生气",
      "img": "https://img3.doubanio.com/icon/u1079617-6.jpg",
      "date": "2016-05-21",
      "content": "皮肤和心&蟋蟀比广受好评的维庸之妻好。真想看完goodbye呀"
    },
    {
      "rate": "3",
      "user": "柴犬妹妹",
      "img": "https://img3.doubanio.com/icon/u1471190-93.jpg",
      "date": "2016-05-08",
      "content": "“实用性的苦恼，仅凭吃饭就能一笔勾销的苦恼，或许才是最强烈的痛苦。”本书吧～真是～论一个富二代的自怨自哀。"
    },
    {
      "rate": "5",
      "user": "小圈",
      "img": "https://img3.doubanio.com/icon/u1799314-1.jpg",
      "date": "2017-02-12",
      "content": "如果我露出了真身 可否被抱紧"
    },
    {
      "rate": "4",
      "user": "亞麻君",
      "img": "https://img3.doubanio.com/icon/u3180126-250.jpg",
      "date": "2017-07-22",
      "content": "太宰治最后自杀了还是好事，他真的不适合这个社会。文字处处揭示社会的阴暗却越是苍白无力，越是狡猾装腔作势之人越顺应社会。所以生而为人对不起。"
    }
  ],
  "tags": [
    {
      "title": "太宰治"
    },
    {
      "title": "悲观"
    },
    {
      "title": "日本文学"
    },
    {
      "title": "【日】太宰治"
    },
    {
      "title": "失去为人的资格"
    },
    {
      "title": "日本"
    },
    {
      "title": "文学"
    },
    {
      "title": "无赖派文学"
    }
  ],
  "author": "太宰治",
  "publisher": " 作家出版社",
  "price": " 25.00元",
  "isbn": "9787506380263",
  "image": "https://img1.doubanio.com/view/subject/l/public/s29118837.jpg",
  "rate": 8.2,
  "alt": "https://book.douban.com/subject/26647769/",
  "title": "人间失格",
  "summary": "\n    收录《人间失格》《维庸之妻》《Good-bye》《灯笼》《满愿》《美男子与香烟》《皮肤与心》《蟋蟀》《樱桃》"
}
```

关注公众号：**正版乔**，我们聊聊

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190527103103532-1394830677.png)
