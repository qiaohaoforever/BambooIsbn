# DoubanBook

http://api.feelyou.top

http://api.feelyou.top

http://api.feelyou.top

老接口所在服务器于2021-03-25到期，届时book.feelyou.top将无法访问。

目前还在使用此接口的朋友们请注意更换新接口：http://api.feelyou.top，暂时无法https，查询方法照旧。

update:

提供新的查询书籍完整目录；

为防止大规模爬虫再次干扰，本次接口加入`key-auth`认证，联系作者公众号发送`isbn-apikey`，获取公共apikey; 如需申请个人apikey，请详细描述项目情况及调用频率。

望天长地久💑

-------

**赞赏支持**

感谢各位朋友对此项目的关注支持，赞赏支持将全部投入到服务器的维护与开发中，确保接口更加稳定、快速，天长地久～

[🍞 面包多/顿顿饭](https://dun.mianbaoduo.com/@qiao)


关注**项目规划**：
https://github.com/qiaohaoforever/DoubanBook/projects




豆瓣读书，自用书籍📚信息查询API2.0
douban_isbn1.0 : https://github.com/qiaohaoforever/DoubanBook/blob/master/douban_isbn1.0.md

## 图书名称查询（暂停供应）
调用地址：https://book.feelyou.top/search/

请求方式：GET

返回类型：JSON

请求示例：https://book.feelyou.top/search/深度学习

#### 请求参数（Query）

| 名称 | 类型   | 是否必须 | 描述          |
| ---- | ------ | -------- | ------------- |
| 书名 | STRING | 必选     | 图书名称 |

#### 返回参数
图书信息列表为list格式，每一本书对应一个json。

| 字段 | 名称 | 类型 | 示例 |
| ---- | ---- | ---- | ---- |
| title | 书名 | str | "深度学习" |
| id | douban书籍编码 | int | 27087503 |
| cover_url | 封面图片 | str | "https://img3.doubanio.com/view/subject/l/public/s29518349.jpg" |
| topics | 话题 | list| [] |
| labels | 标签 | list | [] |
| abstract | 简介 | str | "[美] 伊恩·古德费洛 / [加] 约书亚·本吉奥 / [加] 亚伦·库维尔 / 赵申剑 / 黎彧君 / 符天凡 / 李凯 / 人民邮电出版社 / 2017-7-1 / 168" |
| url | 图书页面 | str | "https://book.douban.com/subject/27087503/" |
| rating | 评分 | dict | {"count": 839,"rating_info": "","star_count": 4,"value": 8.3} |


![](https://pic.downk.cc/item/5e411c8d2fb38b8c3c770b3e.png)

```
[
  {
    "tpl_name": "search_simple",
    "title": "[丛书] 深度学习系列",
    "abstract": ";机械工业出版社;清华大学出版社 / 共11册",
    "url": "https://book.douban.com/series/45479",
    "id": 45479,
    "labels": [
      
    ]
  },
  {
    "tpl_name": "search_subject",
    "title": "深度学习",
    "id": 27087503,
    "cover_url": "https://img3.doubanio.com/view/subject/l/public/s29518349.jpg",
    "topics": [
      
    ],
    "label_actions": [
      
    ],
    "labels": [
      
    ],
    "abstract": "[美] 伊恩·古德费洛 / [加] 约书亚·本吉奥 / [加] 亚伦·库维尔 / 赵申剑 / 黎彧君 / 符天凡 / 李凯 / 人民邮电出版社 / 2017-7-1 / 168",
    "url": "https://book.douban.com/subject/27087503/",
    "abstract_2": "",
    "extra_actions": [
      
    ],
    "interest": null,
    "more_url": "onclick=\"moreurl(this,{i:'0',query:'%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0',subject_id:'27087503',from:'book_subject_search',cat_id:'1001'})\"",
    "rating": {
      "count": 839,
      "rating_info": "",
      "star_count": 4,
      "value": 8.3
    }
  },
  {
    "id": 30293801,
    "title": "Python深度学习",
    "cover_url": "https://img3.doubanio.com/view/subject/l/public/s29839337.jpg",
    "labels": [
      
    ],
    "label_actions": [
      
    ],
    "extra_actions": [
      
    ],
    "rating": {
      "value": 9.6,
      "count": 461,
      "rating_info": "",
      "star_count": 5
    },
    "abstract": "[美] 弗朗索瓦•肖莱 / 张亮 / 人民邮电出版社 / 2018-8 / 119.00元",
    "topics": [
      
    ],
    "more_url": "onclick=\"moreurl(this,{i:'1',query:'%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0',subject_id:'30293801',from:'book_subject_search',cat_id:'1001'})\"",
    "url": "https://book.douban.com/subject/30293801/",
    "abstract_2": "",
    "tpl_name": "search_subject",
    "interest": null
  }
]
```

## ISBN图书查询

![](https://puui.qpic.cn/fans_admin/0/3_823781639_1574958082056/0)

> 自2019年5月8日公布isbn查询接口1.0至今，该图书数据查询服务已被调用八万余次，查得图书**11653**本，感谢一直使用和关心这个接口的朋友们！ 

目前网站域名将于**2019年12月11日**到期，~~qiaohaoforever.cn~~域名将停止服务，请目前还是使用此域名接口的朋友注意调整新的接口，如有不便之处请多包涵。  

#### 关于更新
图书信息查询`isbn2.0`接口新增了部分开发者感兴趣的字段，`图书简介、作者简介、目录、原文摘要、评论赞同数`等，具体请见下方字段说明。针对外国书刊译者信息不统一的情况，这里采用图书摘要的字段显示`作者、译者、出版社、出版时间、价格`等。后期更新，字段以目前版本为主，尽量不改变现有字段含义，增加新的字段名。  

#### 架构调整
在服务架构上也做了一些调整，1.0版本为单机服务，2.0版本采用两台服务器`负载均衡`的方式分担压力，缓存机制优化等。  

#### 关于爬虫
根据日志可以看到，八万多次调用中也有明显的爬虫调用迹象，作为一名开发爱好者，我深刻的清楚大家没有办法忍住看到接口不爬的感情，为了服务于大家的热情，我并没有在反爬虫的方向做太苛刻的防守，但太过高频的爬虫容易触发豆瓣的`反爬虫机制`，导致接口无法获取最新的图书信息，所以，对于`爬虫单位时间爬取频率`做了部分限制🚫，望各位爬虫老哥记得设置一下爬取间隙，稍微sleep一下，温柔一点，哈哈哈😂  

#### ISBN图书查询接口说明

调用地址：http://book.feelyou.top/isbn/ISBN

请求方式：GET

返回类型：JSON

请求示例：http://book.feelyou.top/isbn/9787506380263

#### 请求参数（Query）

| 名称 | 类型   | 是否必须 | 描述          |
| ---- | ------ | -------- | ------------- |
| ISBN | STRING | 必选     | 10-13位ISBN码 |

#### 字段说明

| 首级标签 | 名称        | 类型   | 示例值                                                        | 描述             |
| -------- | ----------- | ------ | ------------------------------------------------------------ | ---------------- |
|          | create_time |        | 2019-11-05 14:25:09                                          | 初次查询时间，统计使用，开发者可忽略|
|          | isbn        | string | 9787506380263                                                | 图书isbn码        |
|          | title       | string | 人间失格                                                      | 书名             |
|          | abstract    | string | 太宰治 / 杨伟 / 作家出版社 / 2015-8 / 25.00元                    | 图书摘要（作者、译者、出版社、出版时间、价格等）|
|          | book_intro  | string | 收录《人间失格》《维庸之妻》《Good-bye》《灯笼》《满愿》《美男子与香烟》《皮肤与心》《蟋蟀》《樱桃》| 图书简介          |
|          | author_intro| string | 太宰治，“私小说”领域的天才。与川端康成、三岛由纪夫齐名，被视为日本战后文学的巅峰人物，后人称其为“无赖派大师”。 | 作者简介 |
|          | catalog     | string | 人间失格/001\n维庸之妻/101\nGood-bye/128\n灯笼/167\n满愿/174\n美男子与香烟/177\n······\n(更多)"| 目录。页面无目录时,字段为[] |
|          | original_texts| list | ["一旦别人问起自己想要什么，那一刹那反倒什么都不想要了。怎么样都行，反正不可能有什么让我快乐的东西——这种想法陡然掠过我的脑海。 (查看原文)\n\n            \n\n\n\n\nmona其实在阴笑\n9 回复\n2012-02-24 14:52:00\n\n\n                —— 引自第14页","胆小鬼连幸福都会害怕，碰到棉花都会受伤，有时还会被幸福所伤。 (查看原文)\n\n            \n\n\n\n\nwheat\n4 回复\n2012-06-23 21:55:39\n\n\n                —— 引自第35页"]| 原文摘录，无此项时为[],根据换行符区分内容             |
|          | labels      | list   | ["太宰治","悲观","日本文学","【日】太宰治","失去为人的资格","日本","无赖派文学","文学"]  |  标签🏷️            |
|          | cover_url   | string | https://img1.doubanio.com/view/subject/l/public/s29118837.jpg | 图书封面图片       |
|          | url         | string | https://book.douban.com/subject/26647769/                     | 该图书豆瓣页面      |
| rating   | count       | int    | 25979                                                         | 参与评分人数       |
| rating   | rating_info | string | 暂无评分                                                        | 暂无评分或评分人数不够等信息 |
| rating   | star_count  | float  | 4                                                             | 评分星🌟       |
| rating   | value       | float  | 8.2                                                           | 图书总评分       |
| comments | user_name   | string | 小莉啊                                                         | 豆瓣用户昵称     |
| comments | user_page   | string | https://www.douban.com/people/lianhuaroad/                    | 豆瓣用户个人页    |
| comments | user_pic    | string | https://img1.doubanio.com/icon/u47055426-37.jpg               | 豆瓣用户头像     |
| comments | vote        | string | 483                                                           | 评论支持数      |
| comments | rate        | int    | 50                                                            | 单个豆瓣用户评分 |
| comments | time        | string | 2016-09-27                                                    | 评论发布时间     |
| comments | content     | string | 太宰治唯恐一生过得不失格                                          | 评论内容         |
|          | source      | string | mongodb、redis、web                                            | 数据来源，统计使用，开发者可忽略 |


#### 正常返回结果示例

```json
{
  "create_time": "2019-11-28 17:18:34",
  "isbn": "9787506380263",
  "title": "人间失格",
  "abstract": "太宰治 / 杨伟 / 作家出版社 / 2015-8 / 25.00元",
  "book_intro": "收录《人间失格》《维庸之妻》《Good-bye》《灯笼》《满愿》《美男子与香烟》《皮肤与心》《蟋蟀》《樱桃》",
  "author_intro": "太宰治，“私小说”领域的天才。与川端康成、三岛由纪夫齐名，被视为日本战后文学的巅峰人物，后人称其为“无赖派大师”。",
  "catalog": "人间失格/001\n维庸之妻/101\nGood-bye/128\n灯笼/167\n满愿/174\n美男子与香烟/177\n······\n(更多)",
  "original_texts": [
    "一旦别人问起自己想要什么，那一刹那反倒什么都不想要了。怎么样都行，反正不可能有什么让我快乐的东西——这种想法陡然掠过我的脑海。 (查看原文)\n\n            \n\n\n\n\nmona其实在阴笑\n9 回复\n2012-02-24 14:52:00\n\n\n                —— 引自第14页",
    "胆小鬼连幸福都会害怕，碰到棉花都会受伤，有时还会被幸福所伤。 (查看原文)\n\n            \n\n\n\n\nwheat\n4 回复\n2012-06-23 21:55:39\n\n\n                —— 引自第35页"
  ],
  "labels": [
    "太宰治",
    "悲观",
    "日本文学",
    "【日】太宰治",
    "失去为人的资格",
    "日本",
    "无赖派文学",
    "文学"
  ],
  "cover_url": "https://img1.doubanio.com/view/subject/l/public/s29118837.jpg",
  "url": "https://book.douban.com/subject/26647769/",
  "rating": {
    "value": 8.2,
    "count": 26240,
    "rating_info": "",
    "star_count": 4
  },
  "comments": [
    {
      "user_name": "小莉啊",
      "user_page": "https://www.douban.com/people/lianhuaroad/",
      "user_pic": "https://img1.doubanio.com/icon/u47055426-37.jpg",
      "vote": "486",
      "rate": "50",
      "time": "2016-09-27",
      "content": "太宰治唯恐一生过得不失格"
    },
    {
      "user_name": "3乐",
      "user_page": "https://www.douban.com/people/Smoldering/",
      "user_pic": "https://img3.doubanio.com/icon/u2394018-4.jpg",
      "vote": "320",
      "rate": "40",
      "time": "2016-01-29",
      "content": "人间失格这一篇读了很久，很难。不太了解作者所以也无法了解这篇里的不堪。后面的短篇很精彩，goodbye的戛然而止真是令人扼腕。要重读。"
    },
    {
      "user_name": "小丑向月亮生气",
      "user_page": "https://www.douban.com/people/eluard_yazu/",
      "user_pic": "https://img9.doubanio.com/icon/u1079617-6.jpg",
      "vote": "157",
      "rate": "50",
      "time": "2016-05-21",
      "content": "皮肤和心&蟋蟀比广受好评的维庸之妻好。真想看完goodbye呀"
    },
    {
      "user_name": "柴犬妹妹",
      "user_page": "https://www.douban.com/people/rosvita/",
      "user_pic": "https://img3.doubanio.com/icon/u1471190-94.jpg",
      "vote": "148",
      "rate": "30",
      "time": "2016-05-08",
      "content": "“实用性的苦恼，仅凭吃饭就能一笔勾销的苦恼，或许才是最强烈的痛苦。”本书吧～真是～论一个富二代的自怨自哀。"
    },
    {
      "user_name": "小圈",
      "user_page": "https://www.douban.com/people/lycle/",
      "user_pic": "https://img3.doubanio.com/icon/u1799314-1.jpg",
      "vote": "110",
      "rate": "50",
      "time": "2017-02-12",
      "content": "如果我露出了真身 可否被抱紧"
    },
    {
      "user_name": "亞麻君",
      "user_page": "https://www.douban.com/people/gongyangfan/",
      "user_pic": "https://img3.doubanio.com/icon/u3180126-250.jpg",
      "vote": "71",
      "rate": "40",
      "time": "2017-07-22",
      "content": "太宰治最后自杀了还是好事，他真的不适合这个社会。文字处处揭示社会的阴暗却越是苍白无力，越是狡猾装腔作势之人越顺应社会。所以生而为人对不起。"
    },
    {
      "user_name": "木昜先生",
      "user_page": "https://www.douban.com/people/69034301/",
      "user_pic": "https://img9.doubanio.com/icon/u69034301-6.jpg",
      "vote": "61",
      "rate": "40",
      "time": "2017-04-14",
      "content": "为什么一个一心作死的家伙还这么有女人缘？"
    },
    {
      "user_name": "流浪の小圆头",
      "user_page": "https://www.douban.com/people/aaaaaaaaaaa/",
      "user_pic": "https://img3.doubanio.com/icon/u48329159-101.jpg",
      "vote": "52",
      "rate": "40",
      "time": "2017-04-01",
      "content": "我的双乳之间是泪水的溪谷。"
    },
    {
      "user_name": "Neski.",
      "user_page": "https://www.douban.com/people/loveasondepp/",
      "user_pic": "https://img9.doubanio.com/icon/u4027330-56.jpg",
      "vote": "68",
      "rate": "30",
      "time": "2016-05-15",
      "content": "之前读过一遍人间失格，只记得我不太喜欢这个故事，总觉得男主有点.....怎么说...作？后来故事忘的一干二净，最近重读了这本收录别的短片的，依然不喜欢这个故事，太宰治的一生都像一个正在建立三观的中二少年，可是他却又对自己看的如此透彻，他就像那个一直在装睡的人，连他自己都不愿醒来。字里行间能感受到的是一种病态的抓狂，就像暴食症患者明明吃到吐明明知道并不那么美味却还在不断的往嘴里塞东西，这不是我们常说的，错的，就停下来这么简单"
    },
    {
      "user_name": "筑舟岛",
      "user_page": "https://www.douban.com/people/60792379/",
      "user_pic": "https://img3.doubanio.com/icon/u60792379-23.jpg",
      "vote": "82",
      "rate": "40",
      "time": "2016-03-04",
      "content": "早就听到太宰治的大名。这本人间失格，却是一个中篇和短篇的合集。高尔基评价太宰治：一方面带着自身经历主人公的挣扎；另一方面坦然描述血的事实。确实很中肯。\ngoodbye这篇，很有推理悬疑小说的感觉，然而未完成，让人好挂念。\n这本书的流行，让我有些纳闷。此书常常以第一人称写惨淡的生活，然而不大让读者感觉其惨淡，这是它的高明处。如果说，这本我们看到的译本，就是太宰治的水准代表的话，他是名实不符的。"
    }
  ],
  "source": "web"
}
```

#### 关于未来

你的赞赏才让我们有更长久的未来！

一定有很多朋友实现了自己的小程序，可以分享在这里，大家体验体验，学习探讨一下～  


`微信公众号：正版乔`

![](https://img2018.cnblogs.com/blog/1548394/201905/1548394-20190527103103532-1394830677.png)
