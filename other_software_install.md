(1) 安装搜狗输入法
## 参考链接

https://blog.csdn.net/lupengCSDN/article/details/80279177

## relied packages

sudo apt install fcitx

## download sougoupinyin and run
sudo dpkg -i sougoupinyinxxxx.deb

## if error, just run

sudo apt  --fix-broken install


(2)安装QQ和微信

## 1.安装依赖

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