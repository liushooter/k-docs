  YOUKU_CLIENT_ID: '2a37c063db2b6103'
  YOUKU_CLIENT_SECRET: '3b369a60040a9b678e2776be7d6d34b3'

***
用户上传的视频(videos/by_user)

https://openapi.youku.com/v2/videos/by_user.json?client_id=2a37c063db2b6103&user_id=UMjUxMTAxNDU2&count=1 

http://open.youku.com/docs/tech_doc.html

```
{
    total: "386",
    page: "1",
    count: "1",
    videos: [
        {
            id: "XNzQ2NjcyNzIw",
            title: "洋洋访谈 福州站 到底该唱多还是该唱空？",
            link: "http://v.youku.com/v_show/id_XNzQ2NjcyNzIw.html",
            thumbnail: "http://g2.ykimg.com/0100641F4653D40D7D4AAA03BDE044FA2DB809-EE1C-AF90-596B-60CD8A7948CA",
            duration: "1298.88",
            category: "生活",
            state: "normal",
            view_count: 79,
            favorite_count: "0",
            comment_count: "1",
            up_count: 0,
            down_count: 0,
            published: "2014-07-27 02:39:23",
            operation_limit: [
                
            ],
            streamtypes: [
                "hd2",
                "flvhd",
                "mp4",
                "3gphd"
            ],
            public_type: "all"
        }
    ]
}
```

***

单条视频详细信息(videos/show)

http://open.youku.com/docs/api_videos.html#videos-show

https://openapi.youku.com/v2/videos/show.json?client_id=2a37c063db2b6103&video_id=XNzQ4MTkzODIw

```
{
    id: "XNzQ4MTkzODIw",
    title: "洋洋访谈 JUA.com理财平台--富国基金赵国峰搬砖理财项目",
    link: "http://v.youku.com/v_show/id_XNzQ4MTkzODIw.html",
    thumbnail: "http://g3.ykimg.com/0100641F4653D7AD7EC4FA188C8A04AE6C261D-AC87-17F9-651E-D28A6FF17362",
    bigThumbnail: "http://g3.ykimg.com/1100641F4653D7AD7EC4FA188C8A04AE6C261D-AC87-17F9-651E-D28A6FF17362",
    duration: "909.15",
    category: "教育",
    state: "normal",
    created: "2014-07-30 07:08:59",
    published: "2014-07-30 07:10:50",
    description: "JUA.com理财平台--富国基金赵国峰搬砖理财项目介绍",
    player: "http://player.youku.com/player.php/sid/XNzQ4MTkzODIw/v.swf",
    public_type: "all",
    copyright_type: "original",
    user: {
        id: "62775364",
        name: "洋洋访谈",
        link: "http://v.youku.com/user_show/id_UMjUxMTAxNDU2html"
    },
    tags: "洋洋访谈,比特币,宝二爷,jua,富国基金,赵国峰,搬砖,套利,理财,JUA.com",
    view_count: 547,
    favorite_count: "0",
    comment_count: "2",
    up_count: "0",
    down_count: "0",
    operation_limit: [
        
    ],
    streamtypes: [
        "hd2",
        "flvhd",
        "hd",
        "3gphd"
    ],
    source: {
        id: "1",
        name: "优酷站内WEB上传",
        link: "http://www.youku.com/v_up/"
    }
}
```