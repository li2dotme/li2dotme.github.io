---
layout: post
title: Markdown Test
category: 
tags:
description: this is a post description, you can use variable {{post.description}} to show it in wherever you want.
---

# ����1 

## ����1.1
 
### ����1.1.1

#### ����1.1.1.1

# ���� 2
 
- �б�1
 
����
 
- �б�2
- �б�3
 
<!-- more -->
 
ˮƽ��
 
----------------------------
 
1. �б�1
2. �б�2
3. �б�3
5. ˳����˲��õ���
3. д����б����Զ�����
 
 
������ֺ��������ˮƽ�ߣ�������ʲôЧ��
---------------------
 
Ư���Ĵ��룬�������Զ�����


    int i = 0;
    i = 1;
    for (int i = 0; i < 100; i++)
    {
        printf("hello markdown!\n");
    }

```c    
int i = 0;
i = 1;
for (int i = 0; i < 100; i++)
{
    printf("hello markdown!\n");
}
```

```html
<div class="qrcodeTable"></div>
<header class="post-header">
    <img class="post-avatar" height="48" width="48"
         src="{{ page.avatarimg }}">

    <h2 class="post-title">{{ page.title }}</h2>

    <p class="post-meta">By {{ page.date | date: "%m" }}��{{ page.date | date: "%d" }}��  {{ page.date | date: "%Y" }}
            <!-- weiyi.theme.modify �޸�tagö�ٴ���
            �ο�hpstr�����post.html -->
            <a
            class="post-categorybut " href="/type/#{{ post.categories  }}">{{ page.categories  }}
            </a>
            <a
            class="post-category " {% for tag in page.tags %}<a href="{{ site.url }}/tags/#{{ tag }}" title="Pages tagged {{ tag }}" class="post-category">{{ tag }}</a>{% unless forloop.last %}{% endunless %}{% endfor %}
            </a>
    </p>
</header>
```


This is a sentence.[^1]

���ڴ���`main(){return 0}` 
���ڴ��� main(){return 0} 

 
*����б��*
�����������棬**���Ǵ���**���ܼ�
__���Ǵ���__


���Ǳ��

| ��Ҫƥ���      | BRE         | ERE       |
|:--------------: |:-----------:|:---------:|
| �ظ�5��a        | `a\{5\}`    | `a{5}`    |
| �ظ�5��10��a    | `a\{5,10\}` | `a{5,10}` |
 

> ��������

"����˫����"


[^1]: This is a footnote.




``` bash

```

<!-- more -->

description: 
