# heroku-vless
Deploy VLESS server to heroku

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/ymcoming/heroku-vless.git)

# VLESS Client Setup

| Connection Variables | Values |
| -------------------- | ------ |
| `Address` | yourAppName.herokuapp.com </br> Cloudflare Reverse Proxy IP |
| `SNI` | Same as Host |
| `AllowInsecure` | false |
| `Port` | 443 |
| `Host` | yourAppName.herokuapp.com </br> Cloudflare Reverse Proxy Domain Name |
| `Path` | /$ID-vless?ed=2048 |
| `id` | Generate using UUID generator |
| `Flow` | xtls-rprx-direct |
| `encryption` | none |
| `Transport` | ws |
| `Tls` | Tls must open, otherwise you will be disconnected |

# Client Ws+Tls+Xtls-rprx-direct(Flow) Support Status

| Client | Status |
| ------ | ------ |
| `2dust V2RayN` </br> `2dust V2RayNG` | Ws+Tls+Flow |
| `OpenWrt SSRPlus` | Ws+Tls |
| `OpenWrt Passwall` | Ws+Tls |
| `QV2Ray` | Ws+Tls |

# Cloudflare Reverse Proxy Code

```
const SingleDay = 'appname.herokuapp.com'
const DoubleDay = 'appname.herokuapp.com'
addEventListener(
    "fetch",event => {
    
        let nd = new Date();
        if (nd.getDate()%2) {
            host = SingleDay
        } else {
            host = DoubleDay
        }
        
        let url=new URL(event.request.url);
        url.hostname="appname.herokuapp.com";
        let request=new Request(url,event.request);
        event. respondWith(
            fetch(request)
        )
    }
)
```
# Caddyindexpage (Welcome to Pull Requests)
Select the link address you like and copy it as the variable CADDYIndexPage variable value
| Number | Address |
| ------ | ------- |
| 1(default) | [Welcome to caddy page](https://raw.githubusercontent.com/caddyserver/dist/master/welcome/index.html) |
| 2 | [3DCEList Periodic Table of Elements](https://github.com/wulabing/3DCEList/archive/master.zip) |
| 3 | [Spotify-Landing-Page-Redesign](https://github.com/WebDevSimplified/Spotify-Landing-Page-Redesign/archive/master.zip) |
| 4 | [dev-landing-page](https://github.com/flexdinesh/dev-landing-page/archive/master.zip) |
| 5 | [free-for-dev](https://github.com/ripienaar/free-for-dev/archive/master.zip) |
| 6 | [tailwindtoolbox-Landing-Page](https://github.com/tailwindtoolbox/Landing-Page/archive/master.zip) |
| 7 | [sandhikagalih/simple-landing-page](https://github.com/sandhikagalih/simple-landing-page/archive/master.zip) |
| 8 | [StartBootstrap/startbootstrap-new-age](https://github.com/StartBootstrap/startbootstrap-new-age/archive/master.zip) |
| 9 | [mikutap A fun page with music](https://github.com/AYJCSGM/mikutap/archive/master.zip) [demo](https://aidn.jp/mikutap) |
| 10 | [WebGL Fluid simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/archive/master.zip) [demo](https://paveldogreat.github.io/WebGL-Fluid-Simulation/) |
| 11 | [loruki-website](https://github.com/bradtraversy/loruki-website/archive/master.zip) |
| 12 | [bongo.cat A musical cat](https://github.com/Externalizable/bongo.cat/archive/master.zip) [demo](https://bongo.cat/) |

# Acknowledgments

- [Project V](https://github.com/v2ray/v2ray-core.git)
- [Project X](https://github.com/XTLS/Xray-core.git)
- [HeroKu](https://heroku.com)
- [heroku-vless](https://github.com/DanyTPG/heroku-vless.git)
- [Better Cloudflare IP](https://github.com/XIU2/CloudflareSpeedTest.git)

# New Features

Websocket 0-RTT import (Just add at the end of path /examples?ed=2048) (2021.3.16)

Client and Server Xray-core 1.4.0+ required!!

Caddy reverse proxy supported (2021.3.29)

# 重要信息
新用户只需要修改id和Caddy主页配置即可

不熟悉caddy配置的不要修改caddy配置

严禁滥用，因滥用出现的所有问题本人概不负责，且用且珍惜！

本项目不宜做为长期翻墙使用。

出于安全考量，请使用cdn，不要使用自定义域名，以实现VLESS+WS+TLS。

# Important information
New users only need to modify the id and Caddy homepage configuration

Do not modify the caddy configuration if you are not familiar with the caddy configuration

Abuse is strictly prohibited, I am not responsible for all problems arising from abuse, and use and cherish!

This project is not suitable for long-term use over the wall.

For security reasons, please use cdn instead of custom domain names to achieve VLESS+WS+TLS.
