一键搭建 VPN shadowsocks/搭建shadowsocksR的shell脚本，一键脚本适用Vultr上的和搬瓦工所有机型（CentOS、Ubuntu、Debian），搭建ss服务器支持所有客户端类型，本机你是iOS，Android，Windows，Mac，或者是Linux。一键脚本内容包括一键搭建shadowsocks/一键搭建shadowsocksR+一键开启bbr加速。

相关文章：



什么是shadowsocks
shadowsocks可以指一种SOCKS5的加密传输协议，也可以指基于这种加密协议的各种数据传输包。shadowsocks正常工作需要服务器端和客户端两端合作实现，首先，客户端（本机）通过ss（shadowsocks）对正常的访问请求进行SOCK5加密，将加密后的访问请求传输给ss服务器端，服务器端接收到客户端的加密请求后，解密得到原始的访问请求，根据请求内容访问指定的网站（例如Google，YouTube，Facebook，instagram等），得到网站的返回结果后，再利用SOCKS5加密并返回给客户端，客户端通过ss解密后得到正常的访问结果，于是就可以实现你直接访问该网站的“假象”。

为什么选择shadowsocks？不限终端（安卓，苹果，Windows，Mac都可用），流量便宜（服务器500G只要15元），方便（一键脚本，不需要专业知识）。

为什么要自己搭建ss/ssr？你也许会觉得买ss服务也很方便，但是你得要考虑以下几个问题。首先，买的ss服务，限制很多，终端可能只能同时在线2个，每个月就一点点流量可能价格却不便宜，有时候还被别人做手脚，流量跑的贼快；其次，别人收钱跑路怎么办？很多这种情况的；更重要的是，如第一个问题中描述的shadowsocks原理，如果有心人做了一点手脚，是可以得到你的访问记录的；而自己搭建ss/ssr服务，一键脚本也就10来分钟就可以搞定。

一键脚本搭建ss/ssr支持系统版本
脚本系统支持：CentOS 6+，Debian 7+，Ubuntu 12+

注：这个脚本支持的系统版本是指ss服务器的版本（都没看过也没关系，不影响搭建），你本机是Windows、Mac、Linux，或者你想用手机端搭建ss/ssr服务器，安卓和苹果，都是可以的。

服务器购买
服务器推荐Vultr和搬瓦工，一是因为本脚本在这两家的所有VPS都做了测试，二是因为都是老牌VPS服务商，不怕跑路。

Vultr：https://www.vultr.com，最低月付2.5刀/500GB流量每月，推荐使用PayPal绑定Visa/Master信用卡，支持支付宝付款
更新注意: Vultr 服务器2.5美元/月的不提供ipv4地址，不能正常使用，所以只能购买5美元/月的了

搬瓦工：https://bwh1.net，可以访问登录，但是注册账号的时候需要全局才能成功
新用户注册链接：https://bwh1.net/aff.php?aff=32798，支持PayPal/支付宝/Visa/Master付款，最低年付19.99刀/500GB流量每月(已补货，之前售空了)

Vultr 官方发布新活动了，新用户激活账户就送 25 美元！参与推特活动可再获得 3 美元！
1、送 25 美元注册地址：https://www.vultr.com/promo25b/?ref=7371675
需要外币信用卡（Visa 卡等）或 Paypal 账户（可绑定银联卡）才可参与活动，赠送部分有效期一年
2、无 25 美元注册地址：https://www.vultr.com/?ref=7371675
支付宝充值是没有优惠的，想使用 vultr 的请从上面地址注册
3、推特送 3 美元活动地址：https://my.vultr.com/promo/
充值账户后才可以参与这个推特活动
注意：此活动仅限从未注册过 Vultr 的参加，个人注册多个账户可能会被没收赠送金额！
如果自己从未注册过这一家，但是还是没有赠送，可以登录后点击左侧 Support 联系客服进行处理！

一键脚本搭建SS/搭建SSR服务并开启BBR加速
一键脚本搭建SS/搭建SSR服务并开启BBR加速

连接远程Linux服务器
Windows上推荐使用WinSCP+PuTTY，Mac通过Terminal远程连接Linux即可。

WinSCP下载：WinSCP-5.13.2-Setup.exe
PuTTY下载：
putty-0.70-installer.msi
putty-64bit-0.70-installer.msi

使用方法：配置主机IP地址，用户名和密码，登录后，点击命令-在PuTTY中打开

一键脚本搭建SS/搭建SSR服务并开启BBR加速

一键搭建SS/搭建SSR服务
注意，shadowsocks/shadowsocksR这两个只需要搭建一个就可以了！！！！SS与SSR之间的比较一直是各有各的说法，王婆卖瓜自卖自夸。

一键搭建shadowsocks
在购买VPS并用PuTTY连接上你刚购买的VPS后，你将看到如下图所示的界面：

一键脚本搭建SS/搭建SSR服务并开启BBR加速

1.下载一键搭建ss脚本文件，只需要执行一次，卸载ss后也不需要重新下载

git clone https://github.com/flyzy2005/ss-fly
如果提示bash: git: command not found，则先安装git：

Centos执行这个：

yum -y install git
Ubuntu/Debian执行这个：

apt-get -y install git
2.运行搭建ss脚本代码

ss-fly/ss-fly.sh -i password 1024
其中password换成你要设置的shadowsocks的密码即可，最好只包含字母+数字，一些特殊字符可能会导致冲突。而第二个参数1024是端口号，也可以不加，不加默认是1024。

一键脚本搭建SS/搭建SSR服务并开启BBR加速

界面如下就表示一键搭建ss成功了：

一键脚本搭建SS/搭建SSR服务并开启BBR加速

注：如果需要改密码或者改端口，只需要重新再执行一次搭建ss脚本代码就可以了，或者修改/etc/shadowsocks.json这个配置文件。

3.相关ss操作

修改配置文件：vim /etc/shadowsocks.json
停止ss服务：ssserver -c /etc/shadowsocks.json -d stop
启动ss服务：ssserver -c /etc/shadowsocks.json -d start
重启ss服务：ssserver -c /etc/shadowsocks.json -d restart
4.卸载ss服务

ss-fly/ss-fly.sh -uninstall
一键搭建shadowsocksR
再次提醒，如果安装了SS，就不需要再安装SSR了，如果要改装SSR，请按照上一部分内容的教程先卸载SS！！！

1.下载一键搭建ssr脚本(只需要执行一次，卸载ssr后也不需要重新执行)，此步骤与一键搭建ss一致

git clone https://github.com/flyzy2005/ss-fly
2.运行搭建ssr脚本代码

ss-fly/ss-fly.sh -ssr
3.输入对应的参数

执行完上述的脚本代码后，会进入到输入参数的界面，包括服务器端口，密码，加密方式，协议，混淆。可以直接输入回车选择默认值，也可以输入相应的值选择对应的选项：

一键脚本搭建SS/搭建SSR服务并开启BBR加速
全部选择结束后，会看到如下界面，就说明搭建ssr成功了：

Congratulations, ShadowsocksR server install completed!
Your Server IP        :你的服务器ip
Your Server Port      :你的端口
Your Password         :你的密码
Your Protocol         :你的协议
Your obfs             :你的混淆
Your Encryption Method:your_encryption_method
Welcome to visit:https://shadowsocks.be/9.html
Enjoy it!
4.相关操作ssr命令

启动：/etc/init.d/shadowsocks start
停止：/etc/init.d/shadowsocks stop
重启：/etc/init.d/shadowsocks restart
状态：/etc/init.d/shadowsocks status
配置文件路径：/etc/shadowsocks.json
日志文件路径：/var/log/shadowsocks.log
代码安装目录：/usr/local/shadowsocks
5.卸载ssr服务

./shadowsocksR.sh uninstall
一键开启BBR加速
BBR是Google开源的一套内核加速算法，可以让你搭建的shadowsocks/shadowsocksR速度上一个台阶，本一键搭建ss/ssr脚本支持一键升级最新版本的内核并开启BBR加速。

BBR支持4.9以上的，如果低于这个版本则会自动下载最新内容版本的内核后开启BBR加速并重启，如果高于4.9以上则自动开启BBR加速，执行如下脚本命令即可自动开启BBR加速：

ss-fly/ss-fly.sh -bbr
一键脚本搭建SS/搭建SSR服务并开启BBR加速

装完后需要重启系统，输入y即可立即重启，或者之后输入reboot命令重启。

判断BBR加速有没有开启成功。输入以下命令：

sysctl net.ipv4.tcp_available_congestion_control
如果返回值为：

net.ipv4.tcp_available_congestion_control = bbr cubic reno
后面有bbr，则说明已经开启成功了。

客户端shadowsocks/shadowsockR登录使用
shadowsocks客户端下载地址：
Windows客户端: https://github.com/shadowsocks/shadowsocks-windows/releases
Mac客户端: https://github.com/shadowsocks/ShadowsocksX-NG/releases
Linux客户端: https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation
Android/安卓客户端：https://github.com/shadowsocks/shadowsocks-android/releases
iOS客户端：商店搜索Wingy/shadowsocks(美国地区)下载

以Windows为例，依次填入服务器IP，服务器端口，密码，保存配置

一键脚本搭建SS/搭建SSR服务并开启BBR加速

在状态栏右击shadowsocks，勾选开机启动和启动系统代理，在系统代理模式中选择PAC模式，服务器->编辑服务器，一键安装shadowsocks的脚本默认服务器端口是1024，加密方式是aes-256-cfb，密码是你设置的密码，ip是你自己的VPS ip，保存即可。

shadowsockR客户端下载地址：
Windows客户端: https://github.com/shadowsocksrr/shadowsocksr-csharp/releases
Mac客户端: https://github.com/flyzy2005/ss-ssr-clients/raw/master/ssr/SS-X-R.zip
Linux客户端: https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation
Android/安卓客户端：https://github.com/shadowsocksrr/shadowsocksr-android/releases
iOS客户端：商店搜索Wingy/shadowsocks(美国地区)下载

以Windows为例：

一键脚本搭建SS/搭建SSR服务并开启BBR加速
在状态栏右击shadowsocksR，在系统代理模式中选择PAC模式，再左击两次状态栏的图标打开编辑服务器界面，如上图所示，按照自己的服务器配置填充内容，保存即可。

一键脚本GitHub地址：https://github.com/flyzy2005/ss-fly
shadowsocks项目GitHub：https://github.com/shadowsocks
shadowsocksR项目GitHub：https://github.com/shadowsocksrr
