# Steam云激活

还在嫌手动激活俄区Key太麻烦了吗？本项目也许能解决你的烦恼：这是一个实现Steam远程激活功能的**开源**项目，将其部署至俄罗斯的服务器上，再通过浏览器访问相应网页便可远程激活俄区Key。同理，将其部署至国内服务器，访问相应的网页便可在国外激活锁国区的Key。

----------

## 功能

一张图就能告诉你：
![Steam 云挂卡](http://i.imgur.com/MJnbFCE.png)

----------

## 使用

我已在俄罗斯服务器上部署了本项目，您可以在浏览器中访问：[https://stkey.win](https://stkey.win) 使用（项目中所使用的WS技术2011年才指定标准，古董级别的浏览器铁定是不支持的啦，某些手机浏览器也不支持）。

至于国内服务器，稍后应该会部署，如果您愿意无偿提供有稳定的国内服务器（腾讯学生机就行），请联系我~ 本系统不会占用多少系统资源的！

浏览器载入页面之后，您需要输入Steam账号、密码和手机令牌（暂不支持邮箱验证码），然后输入Key即可激活。系统会显示锁激活的Sub及其SteamDB的链接。

目前本系统还处于公测阶段，欢迎把你激活时或出bug时的截图发在回贴上，我自己都还不知道我这系统怎么样呢，因为我没有那么Key去测试呀。要知道，测试一次就浪费一个key呢！

----------


## 安全

Steam账号是我们每个人的宝贝，安全问题当然是我在开发时最重视的方面。

* 本项目**开源**，[Github地址在此](https://github.com/zyfworks/steam-key)，欢迎点个星星！您可以看到本项目所有的代码，也可以在自己的服务器上部署。

* 项目基于[SteamKit2](https://github.com/SteamRE/SteamKit)的[Node版](https://github.com/seishun/node-steam)开发，大名鼎鼎的[ASF](https://github.com/JustArchi/ArchiSteamFarm)也是基于SteamKit2开发的。

* 本项目后台不会记录您任何敏感信息，并且**隔离**每次访问请求，一旦您**刷新页面**、**关闭页面**或者**5分钟未操作**，服务器会自动断开连接并销毁所有会话数据。

* 网页启用HTTPS、WSS安全传输，保障您的数据在通信时的安全。

* 我尽可能地保障服务器端的安全。哪怕服务器被攻陷了，由于服务器即时销毁所有数据，攻击者也无法取得数据。当然，最后一道防线——手机令牌仍能保证您的账号安全。

----------

## 风险

* 这玩意存在安全风险吗？ 
>答：虽然本系统不会存储您的任何信息，也在连接时启用安全传输，但本人**无法保证**服务器操作系统、Web软件、编程语言和SteamKit2及其衍生库**不存在**任何**未知的**安全漏洞。请记住，没有绝对的安全！

* 激活俄区Key安全吗？
>答：目前**没有**证据能表明跨区激活俄区Key会被小红信问候。不过使用前还是请谨慎考虑，个人选择，风险自担。如果之后出现任何问题，本人概不负责

* [https://stkey.win](https://stkey.win)能激活全球Key吗？
>答：可以激活全球Key。由于[https://stkey.win](https://stkey.win)的后端服务器在俄罗斯，所以激活的Sub会被标记为"RU"，但不会改变Key原本的Sub ID。
如果想远程激活国区Key，请静候国内激活服务器上线。

* 异地登录呢？
>答：本系统需要在服务器上登录您的账号才能激活Key，理论上是异地登录。不过呢，大家都在云挂卡，也没什么问题呀。虽然同时登录应该不会有问题，但本人仍然建议您在云激活时退出已经登录的账号。

----------
sudo apt install -y nodejs nodejs-legacy npm
sudo npm config set registry https://registry.npm.taobao.org
sudo npm install
sudo npm install -g n
sudo n stable
cp config.example.json config.json
vim config.json
sudo nohup node server.js &
