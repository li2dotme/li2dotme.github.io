---
layout: post
title: 【笔记】Git使用总结
category: UTIL
tags: [  ]

---

## git push 每次都要输入用户名和密码
原因是git clone URL使用的是HTTPS，需要**更改为SSH**，并**更新本地的git地址**。
[Git push requires username and password](http://stackoverflow.com/questions/6565357/git-push-requires-username-and-password)
>A common mistake is cloning using the default (HTTPS) instead of SSH. You can correct this by going to your repository, clicking the ssh button left to the URL field and updating the URL of your origin remote like this:
> `git remote set-url origin git@new.url.here`

完成上述两个步骤，再次push会提示一个错误：

```bash
Warning: Permanently added the RSA host key for IP address '' to the list of known hosts.
Permission denied (publickey).
fatal: Could not read from remote repository.
```
接下来需要**[按照官网的教程生成SSH key](https://help.github.com/articles/generating-ssh-keys/)**
这样就可以避免每次push需要输入用户名和密码。

*整理于2015-03-21*

------

## 多个SSH Key问题
但是一个SSH Key只能用于一个Github账号，如果试图把同一个key贴到另一个账号上，Github会提示错误。**我们需要为不同的账号生成不同的key**。

解决办法是建立配置文件`~/.ssh/config`

```sh
# GitHub Account 1
Host github.1	 // 这个名字在稍后用来测试连接：ssh -T git@github.1
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_1

# GitHub Account 2
Host github.2
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_2
```

特别需要注意的是，此时`~/.ssh/`路径下可能没有`id_rsa_1`文件，所以**在生成ssh key的命令中，需要加`-f`选项指明文件，会新建不存在的文件，如果你尝试手动建立这个文件的话，[会出现问题](http://stackoverflow.com/a/29315364/2722270)**：

```sh
ssh-keygen -t rsa -f ~/.ssh/id_rsa_work -C "your@mail.com"
```

参考：
[Multiple GitHub Accounts & SSH Config](http://stackoverflow.com/a/17158985/2722270)
[git生成ssh key及本地解决多个ssh key的问题](http://riny.net/2014/git-ssh-key/)


## [git push前需要切换ssh key](http://stackoverflow.com/a/18725082/2722270)

```sh
ssh-add ~/.ssh/id_rsa_1
git push
```

*整理于2015-03-28*

---

by li2 上海闸北
