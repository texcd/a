部署.

### 服务端

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/texcd/a) 

WS路径为$UUID-[vmess|vless|trojan|ss|socks]格式


**XRay 将在部署时会自动实配安装`最新版本`。**


可以使用Cloudflare的Workers来中转流量，配置为：

```js
addEventListener(
  "fetch", event => {
    let url = new URL(event.request.url);
    url.host = "xxx.herokuapp.com";
    let request = new Request(url, event.request);
    event.respondWith(
      fetch(request)
    )
  }
)
```

