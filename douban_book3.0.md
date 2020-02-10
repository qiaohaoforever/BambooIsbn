# DoubanBook 3.0
[![](https://pic.downk.cc/item/5e411c8d2fb38b8c3c770b3e.png)](https://pic.downk.cc/item/5e411c8d2fb38b8c3c770b3e.png)
## 书名查询
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
  },
  {
    "more_url": "onclick=\"moreurl(this,{i:'2',query:'%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0',subject_id:'33450010',from:'book_subject_search',cat_id:'1001'})\"",
    "cover_url": "https://img3.doubanio.com/view/subject/l/public/s32322795.jpg",
    "labels": [
      
    ],
    "topics": [
      
    ],
    "interest": null,
    "title": "动手学深度学习",
    "tpl_name": "search_subject",
    "rating": {
      "value": 9.3,
      "count": 109,
      "star_count": 4.5,
      "rating_info": ""
    },
    "label_actions": [
      
    ],
    "abstract": "阿斯顿·张（Aston Zhang） / 李沐（Mu Li） / [美] 扎卡里·C. 立顿（Zachary C. Lipton） / [德] 亚历山大·J. 斯莫拉（Alexander J. Smola） / 人民邮电出版社 / 2019-6 / 85.00元",
    "url": "https://book.douban.com/subject/33450010/",
    "abstract_2": "",
    "extra_actions": [
      
    ],
    "id": 33450010
  },
  {
    "extra_actions": [
      {
        "color": "#CF5B40",
        "text": "豆瓣书店有售",
        "url": "https://book.douban.com/subject/30425822/?channel=subject_list&platform=web"
      },
      {
        "color": "#973F31",
        "text": "豆瓣阅读电子版",
        "url": "https://read.douban.com/ebook/107186317/?dcs=search-buylink&dcm=douban&dct=30425822"
      }
    ],
    "tpl_name": "search_subject",
    "abstract": "[美]特伦斯·谢诺夫斯基（Terrence Sejnowski） / 姜悦兵 / 中信出版集团 / 2019-2 / 88",
    "id": 30425822,
    "more_url": "onclick=\"moreurl(this,{i:'3',query:'%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0',subject_id:'30425822',from:'book_subject_search',cat_id:'1001'})\"",
    "topics": [
      
    ],
    "cover_url": "https://img3.doubanio.com/view/subject/l/public/s29971614.jpg",
    "label_actions": [
      
    ],
    "interest": null,
    "url": "https://book.douban.com/subject/30425822/",
    "rating": {
      "rating_info": "",
      "count": 403,
      "star_count": 4,
      "value": 7.6
    },
    "title": "深度学习 : 智能时代的核心驱动力量",
    "abstract_2": "",
    "labels": [
      
    ]
  },
  {
    "topics": [
      
    ],
    "id": 26976457,
    "title": "Tensorflow：实战Google深度学习框架",
    "interest": null,
    "label_actions": [
      
    ],
    "abstract_2": "",
    "labels": [
      
    ],
    "abstract": "郑泽宇 / 顾思宇 / 电子工业出版社 / 2017-2-10 / 79",
    "rating": {
      "star_count": 4,
      "count": 267,
      "rating_info": "",
      "value": 8
    },
    "extra_actions": [
      
    ],
    "cover_url": "https://img3.doubanio.com/view/subject/l/public/s29349250.jpg",
    "more_url": "onclick=\"moreurl(this,{i:'4',query:'%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0',subject_id:'26976457',from:'book_subject_search',cat_id:'1001'})\"",
    "tpl_name": "search_subject",
    "url": "https://book.douban.com/subject/26976457/"
  }
]
```
