<p align="center">
<a href="https://github.com/qiaohaoforever/DoubanBook">
<img src="https://puui.qpic.cn/fans_admin/0/3_823781639_1574958082056/0" />
</a>
</p>

<h1 align="center">竹简 ISBN</h1>

<p align="center">中文ISBN公开信息查询接口，更新日期 2021.06.09</p>

<p align=center>
<a href="https://github.com/qiaohaoforever/DoubanBook"><img src="https://img.shields.io/github/stars/qiaohaoforever/DoubanBook?style=social" alt="GitHub stars"></a>
  <a><img src="https://img.shields.io/badge/%E5%BE%AE%E4%BF%A1%E5%85%AC%E4%BC%97%E5%8F%B7-%E6%AD%A3%E7%89%88%E4%B9%94-brightgreen"></a>
<a href="https://blog.feelyou.top/"><img src="https://img.shields.io/badge/-%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2-blue"></a>
<a href="https://twitter.com/qiaohaoforever"><img src='https://img.shields.io/twitter/follow/qiaohaoforever?style=social'></a>
</p>

***

> 基于多数据源解决当前国内isbn信息分散的问题，由于图书行业内缺乏整体解决方案，各出版社的isbn信息没有一个比较权威的机构进行集中存储和统筹，图书信息化大佬豆瓣因为种种原因关闭了其图书查询接口；
解决图书从业者、app开发者、高校学生课程项目问题，**愿天下没有查不到的isbn**！
> 看书的人，都不会差。


**项目规划 :** https://github.com/qiaohaoforever/DoubanBook/projects

## 使用指南

调用地址：https://api.feelyou.top/isbn/ISBN

请求方式：GET

返回类型：JSON

请求示例：https://api.feelyou.top/isbn/9787506380263

### 请求参数（Query）

| 名称 | 类型   | 是否必须 | 描述          |
| ---- | ------ | -------- | ------------- |
| ISBN | STRING | 必选     | 10-13位ISBN码 |
| **apikey** | STRING | 必选   |  **申请key**  |

### 代码示例
####  curl
```bash
curl --location --request GET 'https://api.feelyou.top/isbn/9787108070371' \
--header 'apikey: ♦️♦️♦️♦️♦️♦️♦️替换申请的apikey♦️♦️♦️♦️♦️♦️♦️♦️'
```

#### python
```python
import requests

url = "https://api.feelyou.top/isbn/9787108070371"

payload={}
headers = {
  'apikey': '♦️♦️♦️♦️♦️♦️♦️替换申请的apikey♦️♦️♦️♦️♦️♦️♦️♦️'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)
```

#### nodejs
```js
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://api.feelyou.top/isbn/9787108070371',
  'headers': {
    'apikey': '♦️♦️♦️♦️♦️♦️♦️替换申请的apikey♦️♦️♦️♦️♦️♦️♦️♦️'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

#### php
```php
<?php
$client = new http\Client;
$request = new http\Client\Request;
$request->setRequestUrl('https://api.feelyou.top/isbn/9787108070371');
$request->setRequestMethod('GET');
$request->setOptions(array());
$request->setHeaders(array(
  'apikey' => '♦️♦️♦️♦️♦️♦️♦️替换申请的apikey♦️♦️♦️♦️♦️♦️♦️♦️'
));
$client->enqueue($request)->send();
$response = $client->getResponse();
echo $response->getBody();
```

### 字段说明

| 首级标签 | 名称        | 类型   | 示例值                                                        | 描述             |
| -------- | ----------- | ------ | ------------------------------------------------------------ | ---------------- |
|          | create_time |        | 2019-11-05 14:25:09                                          | 初次查询时间，统计使用，开发者可忽略|
|          | isbn        | string | 9787506380263                                                | 图书isbn码        |
|          | title       | string | 人间失格                                                      | 书名             |
|book_info | 作者         | string | 太宰治                                                        |                 |
|book_info | 译者         | string | 杨伟                                                          |                 |
|book_info | 出版社       | string | 作家出版社                                                     |                 |
|book_info | 页数         | string | 219                                                         |                 |
|book_info | 出版年       | string | 2015-8                                                        |                 |
|book_info | 定价         | string | 25.00元                                                          |                 |
|book_info | 装帧         | string | 平装                                                        |                 |
|book_info | 丛书         | string | 世界文学名著                                                         |                 |
|          | abstract    | string | 太宰治 / 杨伟 / 作家出版社 / 2015-8 / 25.00元                    | 图书摘要（作者、译者、出版社、出版时间、价格等）|
|          | book_intro  | string | 收录《人间失格》《维庸之妻》《Good-bye》《灯笼》《满愿》《美男子与香烟》《皮肤与心》《蟋蟀》《樱桃》| 图书简介          |
|          | author_intro| string | 太宰治，“私小说”领域的天才。与川端康成、三岛由纪夫齐名，被视为日本战后文学的巅峰人物，后人称其为“无赖派大师”。 | 作者简介 |
|          | catalog     | string | 人间失格/001\n维庸之妻/101\nGood-bye/128\n灯笼/167\n满愿/174\n美男子与香烟/177"| 目录。页面无目录时,字段为[] |
|          | original_texts| list | ["一旦别人问起自己想要什么，那一刹那反倒什么都不想要了。怎么样都行，反正不可能有什么让我快乐的东西——这种想法陡然掠过我的脑海。"]| 原文摘录，无此项时为[],根据换行符区分内容             |
|          | labels      | list   | ["太宰治","悲观","日本文学","【日】太宰治","失去为人的资格","日本","无赖派文学","文学"]  |  标签🏷️            |
|          | cover_url   | string | https://img1.doubanio.com/view/subject/l/public/s29118837.jpg | 图书封面图片       |
|          | url         | string | https://book.douban.com/subject/26647769/                     | 该图书豆瓣页面      |
| rating   | count       | int    | 25979                                                         | 参与评分人数       |
| rating   | rating_info | string | 暂无评分                                                        | 暂无评分或评分人数不够等信息 |
| rating   | star_count  | float  | 4                                                             | 评分星🌟       |
| rating   | value       | float  | 8.2                                                           | 图书总评分       |
| comments | user_name   | string | 小莉啊                                                         | 用户昵称     |
| comments | user_page   | string | https://www.douban.com/people/lianhuaroad/                    | 用户个人页    |
| comments | user_pic    | string | https://img1.doubanio.com/icon/u47055426-37.jpg               | 用户头像     |
| comments | vote        | string | 483                                                           | 评论支持数      |
| comments | rate        | int    | 50                                                            | 单个用户评分 |
| comments | time        | string | 2016-09-27                                                    | 评论发布时间     |
| comments | content     | string | 太宰治唯恐一生过得不失格                                          | 评论内容         |
|          | source      | string | mongodb、redis、web                                            | 数据来源，统计使用，开发者可忽略 |


### 正常返回结果示例

```json
{
    "create_time": "2020-04-03 12:04:11",
    "isbn": "9787506380263",
    "title": "人间失格",
    "book_info": {
        "作者": "太宰治",
        "译者": "杨伟",
        "出版社": "作家出版社",
        "出版年": "2015-8",
        "页数": "219",
        "定价": "25.00元",
        "装帧": "平装",
        "丛书": "世界文学名著",
        "ISBN": "9787506380263"
    },
    "abstract": "太宰治 / 杨伟 / 作家出版社 / 2015-8 / 25.00元",
    "book_intro": "收录《人间失格》《维庸之妻》《Good-bye》《灯笼》《满愿》《美男子与香烟》《皮肤与心》《蟋蟀》《樱桃》",
    "author_intro": "太宰治，“私小说”领域的天才。宇川端康成、三岛由纪夫齐名，被视为日本战后文学的巅峰人物，后人称其为“无赖派大师”。",
    "catalog": "人间失格/001\n维庸之妻/101\nGood-bye/128\n灯笼/167\n满愿/174\n美男子与香烟/177",
    "original_texts": [
        "一旦别人问起自己想要什么，那一刹那反倒什么都不想要了。怎么样都行，反正不可能有什么让我快乐的东西——这种想法陡然掠过我的脑海。 (查看原文)"
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
    "cover_url": "https://img9.doubanio.com/view/subject/l/public/s28323390.jpg",
    "url": "https://book.douban.com/subject/26647769/",
    "rating": {
        "count": 29094,
        "rating_info": "",
        "star_count": 4,
        "value": 8.2
    },
    "comments": [
        {
            "user_name": "小莉啊",
            "user_page": "https://www.douban.com/people/lianhuaroad/",
            "user_pic": "https://img9.doubanio.com/icon/u47055426-37.jpg",
            "vote": "514",
            "rate": "50",
            "time": "2016-09-27",
            "content": "太宰治唯恐一生过得不失格"
        },
        {
            "user_name": "小圈",
            "user_page": "https://www.douban.com/people/lycle/",
            "user_pic": "https://img9.doubanio.com/icon/u1799314-1.jpg",
            "vote": "120",
            "rate": "50",
            "time": "2017-02-12",
            "content": "如果我露出了真身 可否被抱紧"
        },
        {
            "user_name": "人気小圆头",
            "user_page": "https://www.douban.com/people/aaaaaaaaaaa/",
            "user_pic": "https://img9.doubanio.com/icon/u48329159-103.jpg",
            "vote": "63",
            "rate": "40",
            "time": "2017-04-01",
            "content": "我的双乳之间是泪水的溪谷。"
        }
    ],
    "source": "redis"
}
```
### 错误反馈🙅‍♂️
#### 无权限
```json
{
    "message": "Invalid authentication credentials"
}
```

#### 无apikey 
```json
{
    "message": "No API key found in request"
}
```

#### 高频访问
```json
{
    "message": "API rate limit exceeded"
}
```

#### 服务器负载过高，换isbn查询，或者间隔一段时间再请求该isbn
```json
{"error":"The server load is too high. Please try again later."}
```

## apikey 获取

本次接口加入`key-auth`认证，联系作者公众号发送`isbn-apikey`，获取公共apikey; 
*如需申请个人apikey，请详细描述项目情况及调用频率*。


## 赞赏支持

感谢各位朋友对此项目的关注支持，赞赏支持将全部投入到服务器的维护与开发中，确保接口更加稳定、快速，天长地久～

⬇️⬇️⬇️⬇️⬇️⬇️⬇️

[🍞 点这里，请我吃顿饭](https://dun.mianbaoduo.com/@qiao)

-------
## 感谢
 - 豆瓣读书
 - 国家isbn中心
