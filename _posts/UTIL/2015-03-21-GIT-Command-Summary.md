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
2015-03-21整理

---
by li2 上海闸北
