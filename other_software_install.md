# 1. 安装搜狗输入法
## 参考链接

https://blog.csdn.net/lupengCSDN/article/details/80279177

## relied packages

sudo apt install fcitx

## download sougoupinyin and run
sudo dpkg -i sougoupinyinxxxx.deb

## if error, just run

sudo apt  --fix-broken install


# 2. 安装QQ和微信

## (1) 安装依赖

参考链接：

https://forum.ubuntu.org.cn/viewtopic.php?f=73&p=3217021&sid=6194a64cefc1f4c5ac43dcd8729ca3c8

（1）依赖脚本如
```shell
#!/bin/bash
mkdir /tmp/deepintemp
cd /tmp/deepintemp
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-wine_2.18-19_all.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-wine32_2.18-19_i386.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-wine32-preloader_2.18-19_i386.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-helper/deepin-wine-helper_1.2deepin8_i386.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-plugin/deepin-wine-plugin_1.0deepin2_amd64.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-plugin-virtual/deepin-wine-plugin-virtual_1.0deepin3_all.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-uninstaller/deepin-wine-uninstaller_0.1deepin2_i386.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/u/udis86/udis86_1.72-2_i386.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-fonts-wine_2.18-19_all.deb
wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-libwine_2.18-19_i386.deb
wget https://mirrors.aliyun.com/deepin/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_1.5.1-2_amd64.deb
wget https://mirrors.aliyun.com/deepin/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_1.5.1-2_i386.deb

echo '准备添加32位支持'
sudo dpkg --add-architecture i386
echo '添加成功，准备刷新apt缓存信息...'
sudo apt update
echo '即将开始安装...'
sudo dpkg -i *.deb
echo '安装完成，正在自动安装依赖...'
sudo apt install -fy

rm -vfr /tmp/deepintemp
```

（2）从官方下载微信和QQ

https://github.com/wszqkzqk/deepin-wine-ubuntu

sudo dpkg -i xxx

（3）修改中文乱码

https://github.com/wszqkzqk/deepin-wine-ubuntu/issues/136

注意：run.sh&ru_v2.sh中都要修改才生效

（4）安装托盘

https://github.com/phocean/TopIcons-plus

# 3. dropbox

(1) 安装教程

https://websiteforstudents.com/how-to-install-setup-dropbox-on-ubuntu-18-10-18-04-16-04-desktops/

(2) 方法一：下载deb文件，然后再安装

(3) 方法二，使用如下命令安装

```shell
sudo apt-get update
sudo apt-get -y install nautilus-dropbox
```

(4) 使用代理启动

```shell
proxychains dropbox start -i
```

(5) 配置

proxy & path

# 4.SecureCRT

参考链接：

https://blog.csdn.net/idwtwt/article/details/86727895

https://www.cnblogs.com/kevingrace/p/9353963.html

最好的教程：

https://www.52pojie.cn/thread-1000970-1-1.html

1）下载secureCRT和secureFX（安装官方提供的比较可靠）
官网下载地址：https://www.vandyke.com/download/index.html
直接到官网上下载就可以，下载过程可能会提示你要先注册，没关系，直接注册，然后再下载。
我直接下载的是最新版secureCRT+secureFX的合体包：scrt-sfx-8.5.4-1942.ubuntu16-64.x86_64.deb

2）进行安装

sudo dpkg -i scrt-sfx-8.5.4-1942.ubuntu16-64.x86_64.deb
如果安装过程中因为缺少依赖而安装失败，只需要通过命令：apt-get install -f即可完成依赖的安装。
安装后，到Kali的应用搜索里就能找到secureCRT和secureFX工具了。
*******@@@@@@@@********

在启动过程可能会报错，我再启动的时候报错信息是：缺少libpng12.so.0的支持
解决办法是：安装vmware时在vmware的安装目录中有libpng12.so.0，通过链接解决因为缺少环境无法启动

sudo ln -s /usr/lib/vmware/lib/libpng12.so.0/libpng12.so.0 [url=]/usr/lib/x86_64-linux-gnu/libpng12.so.0[/url]

3）secureCRT和secureFX的License破解
破解文件下载：https://share.weiyun.com/5Mc38uB 密码：yetp32

3.1) 运行破解secureCRT脚本
sudo  perl securecrt_forgeek_crack.pl /usr/bin/SecureCRT

启动SecureCRT，根据执行结果填写license信息即可

3.1) 运行破解secureFX脚本
sudo perl securefx_forgeek_crack.pl /usr/bin/SecureFX
启动SecureFX，根据执行结果填写license信息即可

# wps

参考链接

https://blog.csdn.net/jays_/article/details/82752847

# windows 访问linux文件教程及其软件ExtFS的使用

https://www.sdbeta.com/wg/2018/0523/222982.html
