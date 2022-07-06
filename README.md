# 搭建VPN教程/个人vpn搭建/科学上网/2022搭建ss/一键脚本搭建/梯子/翻墙教程/电脑手机使用VPN

现在很多的资料，特别是技术文档等内容，都是发布在国外的网上，但很多很难访问得到，比如 Youtube 上有很多的优质的学习资源，Google 高质量的资源搜索，身为一名技术人，学术者，有一个属于自己的 VPN 就显得尤为重要了。笔者建议不要去购买第三方的 VPN 账号，很多都是有后门的，而搭建一个完全属于自己的 VPN，安全性和自由度都比较高。

那么如何搭建一个属于自己的 VPN 呢？接下来我将从 0 教你实现，以下内容请认真阅读并操作，对于新手来说，10 分钟就能搞定。

## 1、购买境外的云服务器

首先你需要一台境外的服务器，然后在里面搭建一个 VPN，以后你就可以通过这台云服务器访问到外面的世界。

这里推荐使用[搬瓦工云服务器](https://bandwagonhost.com/aff.php?aff=68296)，因为搬瓦工有专门的 CN2 路线，路由直接通向中国，速度会很快。个人使用的话推荐[搬瓦工 CN 加速专用路线-高性价比个人专用搬瓦工 CN2 20G](https://bwh88.net/aff.php?aff=68296&pid=57)。

先别急着下单，有一个隐藏 code 可以使用。

点击进入[搬瓦工服务器 cn2 专用路线](https://bwh88.net/aff.php?aff=68296&pid=57)，接着`鼠标右键点击-查看源代码`，这时候搜索 code：

![搬瓦工 code](https://user-images.githubusercontent.com/98797623/177511758-5b5f26dc-8460-4015-a52e-7467b6d0f091.png)

把这个 code：xxxx 中的 xxx 复制下来。

接着回到刚刚的页面，点击 `Add to cart`

![搭建VPN](https://user-images.githubusercontent.com/98797623/177512145-e664639d-85db-40b5-abe8-4cc8cbb3d2dd.png)

在这里有个输入框，把你刚刚复制的优惠code粘贴到这里，然后点击 `Validate code`


![搭建VPN](githubusercontent.com/98797623/177512532-b227bc29-c88e-4165-8b1e-fc954aa83731.png)

这时候你就可以得到一个更优惠的价格了：

![搭建VPN](https://user-images.githubusercontent.com/98797623/177512799-891bcd7a-9f1d-43e5-856f-45fc7624fa76.png)

接着点击 `checkout`：

![搭建VPN](https://user-images.githubusercontent.com/98797623/177512932-355d9cca-ddd1-4806-b263-4cae753cf68c.png)

使用支付宝：

![搭建VPN](https://user-images.githubusercontent.com/98797623/177513065-77e289a7-4fd3-489f-b879-8533362051a6.png)

稍等片刻，点击菜单【services-myservice】就可以看到属于你自己的服务器了。

点击【KiwiVM Control Panel】进入你的服务器详情，其中【IP address】是你这台服务器的公网 IP，【SSH PORT】是连接到你这台服务器的端口号。 这两个待会会使用到。

## 2. 连接你的服务器

如果你是 Windows 用户，可以下载[putty.exe](https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe)。

打开后，输入你服务器的 IP 地址和 ssh 端口号，点击连接。

如果你是 Linux 或者 Mac 用户，打开终端，然后使用 ssh 命令连接：

`ssh root@服务器IP地址 -p ssh端口号`

> 比如：ssh root@192.168.1.1 -p 2231

## 一键搭建 VPN

安装必要的库：
```
sudo yum -y install wget gcc gcc-c++ autoconf automake make
```

安装 VPN 脚本 ss.sh:
```
wget –no-check-certificate -O ss.sh https://raw.githubusercontent.com/sucong426/VPN/main/ss.sh
```
执行脚本
```
sh ss.sh
```

设置你的 VPN 密码:

<img width="791" alt="119024123-45a90280-b992-11eb-9ea5-514542f71594" src="https://user-images.githubusercontent.com/98797623/177523896-b42d40a0-9b91-480f-a2bc-1f5b0629c25e.png">


接着输入你 VPN 的端口，可以直接回车。

接着输入加密方式，你可以选择 7:

<img width="574" alt="119024193-59546900-b992-11eb-8d71-81681e582e38" src="https://user-images.githubusercontent.com/98797623/177524031-c9a79ddb-5a48-476b-84e0-bf8fa8b798c0.png">


设置好了之后，按一下回车就可以开始安装，稍等一会，出现以下信息说明安装成功：

<img width="645" alt="119024277-6bcea280-b992-11eb-90a9-7fa45cbdc97d" src="https://user-images.githubusercontent.com/98797623/177524090-a6208659-6535-45a0-88eb-69571a1fa14f.png">


这是属于你自己 VPN 的 IP 地址，端口号，密码，加密方式。把它们复制下来，然后就可以使用客户端连接这个代理从而访问Google了。

复制号信息之后，服务器连接可以关掉，它会一直运行。

## windows 使用 VPN

### 下载Shadowsocks Windows客户端

第一步当然是下载啦！了解GitHub的童鞋都会懂得到release页寻找最新版或者历史版本的程序。不了解的童鞋直接点这里：https://github.com/shadowsocks/shadowsocks-windows/releases

下载回来是一个ZIP压缩包。把压缩包里面的唯一一个文件，Shawdowsocks.exe解压放到一个文件夹里，无需安装就可以使用了。

### 安装Microsoft .NET Framework 4.6.2和VC++ 2015 Redistributable


如果你不知道这两个是什么，没关系，下载和安装就是了。不用担心这会增加你的Windows系统多大的负担。这是微软提供的一些组件。就像打乒乓球，你总得要有球拍和球吧？

.Net Framework 4.6.2：https://www.microsoft.com/zh-CN/download/details.aspx?id=53344

VC++ 2015 Redistributable：https://www.microsoft.com/zh-CN/download/details.aspx?id=53840


### 配置Shadowsocks服务器

终于到了戏玉部分了！首先双击刚才下载回来的Shadowsocks。第一次打开，应该会看到这个“编辑服务器”窗口。如果没看到的话，右键点击屏幕右下角的Shadowsocks图标，并点击菜单“服务器”-->“编辑服务器”。

红色方框的四个信息想必你都有了吧。服务器地址可以是IP也可以是一个域名。端口，密码和加密这三个参数务必要和服务器设置的一致。

至于绿色方框里面的备注，就是给这个配置信息的一个名称方便辨认。


![ss_win_guide_01](https://user-images.githubusercontent.com/98797623/177524894-400e2ae8-3392-465d-90e5-ab232d349db0.jpeg)


### 启用系统代理并使用PAC模式


现在我们可以启用Shadowsocks进行代理访问互联网了^_^。不过这里要强调一点，除非特殊需要，务必使用PAC模式。全局模式相当于所有流量都经过代理，国内网站都使用代理的话不是什么好事。不紧速度慢，而且容易暴露服务器。

首先，在右键菜单里面点击“启用系统代理”，客户端就会修改IE的代理设置指向客户端的端口。简而言之，就是让IE通过Shadowsocks代理访问互联网了。然后在“系统代理模式”下，选择“PAC模式”。


![ss_win_guide_02](https://user-images.githubusercontent.com/98797623/177526264-a5ea6457-0ceb-45b4-83ad-d4dbeda71850.jpeg)

# Mac 使用 VPN

## 第一步 安装 ShadowsocksX-NG

在安装之前，请始终确保您的系统满足最低系统要求。

您需要具备 MacOS 10.11 或更高版本才能运行 ShadowsocksX-NG。如果您的操作系统版本较旧， 则请先升级到 MacOS 10.11 或更高版本。按照下面的说明在 MacOS 上下载并安装 ShadowsocksX-NG。

## 下载客户端
https://github.com/shadowsocks/ShadowsocksX-NG/releases/download/v1.8.2/ShadowsocksX-NG.app.1.8.2.zip

## 安装客户端
双击解压 ShadowsocksX-NG.x.x.x.zip , 获取 ShadowsocksX-NG。

将 “ShadowsocksX-NG” 拖移到 “访达”里面的 “应用程序”。



![mac2](https://user-images.githubusercontent.com/98797623/177526629-d8e34015-2884-43fc-8c22-6f00051964fc.gif)


在 “应用程序” 中双击 “ShadowsocksX-NG” > 选择 “打开”。


![mac3](https://user-images.githubusercontent.com/98797623/177526685-698b5a1e-72bf-45ed-a890-311131ac942a.png)

## 配置 Shadowsocks 账号

在您的电脑上， 执行下列操作：
点击屏幕顶部菜单栏的 小飞机> “服务器” > “服务器设置”

<img width="272" alt="mac6" src="https://user-images.githubusercontent.com/98797623/177526825-f8de25c1-7faa-40a4-8c2f-37de7e0247c2.png">

- 点击窗口上的 “+” > 填写 “地址” > 填写 “服务端口” > 选择 ”加密方法”。
- 填写 “密码“ > 填写”备注” 为可选项。
- 点击 “打开Shadowsocks” 。
- 当显示 Shadowsocks: On时，表示系统代理已经打开。

> PAC 模式 表示可以实现自动代理， 及本来可以访问的网站不会经过代理，推荐日常使用。
> 全局模式 表示计算机内大多数流量都会经过代理， 不推荐日常使用。


# Android 使用 VPN

## 下载 Shadowsocks 客户端

点击下载：https://github.com/shadowsocks/shadowsocks-android/releases/download/v4.8.1/shadowsocks-x86-4.8.1.apk

打开软件，点击 + 号，把你的 VPN 信息填进去，开启代理即可。

# iPhone 使用 VPN

苹果手机游览器打开 在线安装：https://shadowsockshelp.github.io/ios/

苹果美区账号分享 详见： https://shadowsockshelp.github.io/Shadowsocks/appleid.html

##  iOS配置 Shadowsocks 客户端

点击右上角的加号进行手动输入


![Shadowrocket7](https://user-images.githubusercontent.com/98797623/177528156-8e876173-a082-4b8a-bcb4-abb979483488.png)

# 使用效果


<img width="1155" alt="截屏2022-07-06 下午6 18 20" src="https://user-images.githubusercontent.com/98797623/177528639-a50553d1-1b7a-4437-9c18-f57a44072f9b.png">

