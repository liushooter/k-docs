
## What is RTMP

[RTMP](http://en.wikipedia.org/wiki/Real_Time_Messaging_Protocol)

RTMP(Real Time Messaging Protocol) 实时消息传输协议最初是由 Macromedia 为互联网上 Flash player 和服务器之间传输音频、视频以及数据流而开发的一个私有协议。

Adobe 收购 Macromedia 购以后，公布了这个协议的一部分，以备公共使用。

## MPEG-DASH

[MPEG-DASH](http://en.wikipedia.org/wiki/Dynamic_Adaptive_Streaming_over_HTTP)

Dynamic Adaptive Streaming over HTTP (DASH), also known as MPEG-DASH.

nginx-rtmp-module support MPEG-DASH

## rtmp player 

html5 video tag  support rtmp ???  还不支持

```
<video>
  <source src="rtmp://localhost/myapp" type="rtmp/mp4">
</video>
```

[jwplayer](http://www.jwplayer.com/)

## rtmp client

[install nginx-rtmp-module](https://github.com/arut/nginx-rtmp-module/wiki/Getting-started-with-nginx-rtmp)

[Getting-started-with-nginx-rtmp](https://github.com/arut/nginx-rtmp-module/wiki/Getting-started-with-nginx-rtmp)

```
### nginx-1.4.7

./configure --add-module=nginx-rtmp-module --with-http_ssl_module   
```


nginx.conf

```
http {
    include       mime.types;
    default_type  application/octet-stream;

 
    sendfile        on;
 
    keepalive_timeout  65;

    gzip  on;

    server {
        listen       80;
        server_name  localhost;

        #charset koi8-r;

        #access_log  logs/host.access.log  main;

        location / {
            root  /Users/liuning/sites/rtmp-publisher;
            index   player.html;
        }

}

rtmp {
    server {
        listen 1935;
        ping 30s;
        notify_method get;

        application myapp { #必须一致
            live on;
        }
    }
}
```


```
ffmpeg -re -i knewcoin.mp4 -c copy -f flv rtmp://localhost/myapp/mystream
```

```
<!DOCTYPE html>
<html>
<head>
    <title>RTMP Player</title>
    <script type="text/javascript" src="swfobject.js"></script>
    <script type="text/javascript">
        var flashVars = {
            streamer: 'rtmp://localhost/myapp',
            file:'mystream'
        };
        var params = {};
        params.allowfullscreen = "true";
        var attributes = {};
        swfobject.embedSWF("RtmpPlayer.swf", "rtmp-publisher", "640", "480", "9.0.0", null, flashVars, params, attributes);
    </script>
</head>
<body>
    <div id="rtmp-publisher">
        <p>Flash not installed</p>
    </div>
</body>
</html>

```

## Server Support

http://www.longtailvideo.com/support/jw-player/28854/using-rtmp-streaming/

In order to use RTMP, your host or CDN needs to have a dedicated RTMP server installed. There are two major offerings, both supported by JW Player:

The Wowza Media Server

The Adobe Media Server
***

流播放

1 rtmp 协议

2 nginx配置 RTMP

3 创建 RTMP服务器

4 从摄像头 获取音视频

5 获取的视频流封装到 rtmp

 