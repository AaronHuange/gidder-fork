[![Build Status](https://travis-ci.org/antoniy/Gidder.svg?branch=master)](https://travis-ci.org/antoniy/Gidder)

Gidder
======

Git server for Android

Available in Google Play: https://play.google.com/store/apps/details?id=net.antoniy.gidder.beta

简要教程 <https://blog.csdn.net/TaylorPotter/article/details/69808733>

#### 使用步骤：

##### 手机端：
    1. 下载apk
    2. 在apk中添加用户(用户要需要填写电脑上.ssh文件的的公钥，而且添加的用户的用户名以及密码要和公钥对应，不对应则用户名密码配置和公钥不匹配、则会连不上。) 
    3. 在apk中添加仓库。(这个没什么好注意的)

##### 电脑端：
     1. 增加ssh-dss支持(Mac电脑为例)
        cd ~/.ssh
        touch config && chmod 600 config
        echo "HostkeyAlgorithms +ssh-dss" >> config
       
     2. 拉代码
        git clone ssh://username@ip:port/reponame.git
        username(试了)、reponame(没试)不管配置是什么统统小写
        拉不下来可能手机端第二步配置不匹配
#shiyong  

