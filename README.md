[![Build Status](https://travis-ci.org/antoniy/Gidder.svg?branch=master)](https://travis-ci.org/antoniy/Gidder)

Gidder
======

#### 使用步骤：

##### 手机端：
1. 下载apk (点击 [下载](./gidder.apk) ). 
2. 在apk中添加用户(用户要需要填写电脑上.ssh文件的的公钥，而且添加的用户的用户名以及密码要和公钥对应，不对应则用户名密码配置和公钥不匹配、则会连不上。) 
3. 在apk中添加仓库。(这个没什么好注意的)
4. 给仓库添加对应用户权限

##### 电脑端：
1. 拉代码
   git clone ssh://username@ip:port/reponame.git
   拉不下来可能手机端第二步配置不匹配





## 常见问题

1. 
 ``` xml
  Cloning into 'xx'...
  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
  @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
  IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
  Someone could be eavesdropping on you right now (man-in-the-middle attack)!
  It is also possible that a host key has just been changed.
  The fingerprint for the DSA key sent by the remote host is
  SHA256:B3Eha27DE1q+JU0fD/60Ms/b9HMVefQ6teD4RY/GzAI.
  Please contact your system administrator.
  Add correct host key in /Users/MacBook/.ssh/known_hosts to get rid of this message.
  Offending DSA key in /Users/MacBook/.ssh/known_hosts:2
  DSA host key for [192.168.1.4]:2222 has changed and you have requested strict checking.
  Host key verification failed.
  fatal: Could not read from remote repository.
  Please make sure you have the correct access rights
and the repository exists.
 ```

  解决方法：
若是由于ip更换出错：


若不是由于ip更换出错：	
  电脑上.ssh/known_hosts记录的是连接过的git服务器，当git服务器的 IDENTIFICATION HAS CHANGED，说明改变了，需要找到ssh/known_hosts中对应的记录删除，或者直接删除ssh/known_hosts文件，然后重新连接，输入yes即可。




2.
 ``` xml
  Cloning into 'aaaa'...
  fatal: Could not read from remote repository.
  Please make sure you have the correct access rights
  and the repository exists.
 ```

  解决方法：
  先尝试 ssh -vT ssh://用户名@ip:port，看是否成功，不成功。则重新生成公钥，在手机上重新配置用户。

  成功则代表仓库有问题，检查手机上是否对该用户配置了push/pull相关权限

  

3. ``` xml
  Unable to negotiate with 10.0.56.163 port 2222: no matching host key type found. Their offer: ssh-dss
  fatal: Could not read from remote repository.
  ```
  
  解决方法：
  在目录文件 ~/.ssh/config (没有则新建)中添加
  HostkeyAlgorithms +ssh-dss




# PS:一个类似 Gidder 的更黑科技的服务器全家桶 Servers Ultimate Pro，支持各种常用服务器，地址请自行搜索


  
  
