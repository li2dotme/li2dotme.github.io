---
layout: post
title: 【笔记】Android 使用ListFragment显示列表
category: ANDROID
tags: [ ]
---

使用 ListFragment(Fragment 的子类) 构建列表视图，



## 使用 ArrayList<E> 和 Singleton 构建应用的模型层

ArrayList<E>是一个支持存放指定数据类型对象的Java有序数组类，具有获取、新增及删除数组中元素的方法。
把列表需要显示的数据集中存储(centralized data storage)在一个单例(Singleton)中。单例是特殊的Java类，一个类只允许创建一个实例。

### 创建单例
需创建一个带有私有构造方法及get()方法的类，其中get()方法返回实例。如实例已存在，get()方法则直接返回它；如实例还未存在，get()方法会调用构造方法来创建它。

```Java
// Setting up the Singleton
public class CrimeLab {
    private static CrimeLab sCrimeLab;
    private Context mAppContext;

    private CrimeLab(Context appContext) {
        mAppContext = appContext;
    }

    public static CrimeLab get(Context c) {

    }


}
```



## 创建 ListFragment

## 使用抽象 activity 托管 fragment

## ListFragment、ListView 及 ArrayAdapter

## 定制 ListItem

---

整理笔记时参考了如下资料：

- 《Android编程权威指南》Bill Phillips  Brian Hardy著，王明发 译。人民邮电第1版。
    英文版书名《Android Programming - The Big Nerd Ranch Guide》

---
李贰 2015-03-15 沪北
