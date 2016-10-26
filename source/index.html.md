---
title: API Reference kaws

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction 簡介

抗癌衛士slate 頁

主要用來展示各種API接口

Wiki: [https://github.com/WYQJ/kaws-all/wiki](https://github.com/WYQJ/kaws-all/wiki)

# Common Address  常用地址


郝思远接口文档：[http://blog.leanote.com/mythhsy ](http://blog.leanote.com/mythhsy)

`git需要登陆`

git文档：[https://github.com/WYQJ/kaws-all/wiki](https://github.com/WYQJ/kaws-all/wiki)

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# APIs-4.30

## 4.30 API
> 代码部分因为无法获取所以暂时没有替换，JSON部分已经替换：

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
      "posts": [
        {
          "id": "ab0fcb13dafc41dbbfa08948ce73af21",
          "title": "Ms 女 u u 婆透明",
          "disp_type": 0,
          "latest_posted_at": "2016-01-21T18:33:07+08:00",
          "comment_num": 32,
          "is_recommended": true,
          "has_images": false,
          "is_recent": false,
          "user": {
            "userkey": "f5bb73f9a4e64b3091a2e3ddf397e104",
            "username": "球球丶思密达",
            "level": 15,
            "avatar_url": "http://7xk154.com1.z0.glb.clouddn.com/288bf06307fe441ea91db05b1d1578f7",
            "diseased_state": {
              "id": 3,
              "name": "胃癌"
            }
          },
          "share_link": "http://support.kangaiweishi.com/community/ab0fcb13dafc41dbbfa08948ce73af21"
        }
      ]
```

### 精品贴列表Boutique post list

`GET /v4/community/posts `

注意是V4不是V3

### Query Parameters

Parameter参数 | Default是否必传 | Description描述
--------- | ------- | -----------
recommend  | false | 传整型1为精品贴,不传或其它无效
hot | flase | 传整型1为热门贴,不传或其它无效
<aside class="warning">
注意：两者互斥 不可同时传1
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

