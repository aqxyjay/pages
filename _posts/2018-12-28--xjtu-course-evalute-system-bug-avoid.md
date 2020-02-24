---
layout: post
title: "西交大课程评价系统问题的规避方案"
author: "Zhangchunxin"
categories: tech
published: false
tags: [前端,MBA,西安交通大学]
---

### 问题1. 点击“课程评教”按钮没有响应

![01](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/01.jpg)

如上图，在查询成绩之前，需要先进行“课程评教”。

使用Chrome、Edge和IE浏览器，点击“课程评教”按钮，没有任何响应。

**规避方案：**
1. 确认已经登录VPN
2. 在浏览器地址栏输入如下地址，可以直接打开评价系统
https://vpn.xjtu.edu.cn/web/1/http/0/gste.xjtu.edu.cn/index.do

*如果是校园内网，输入的地址应该是 https://gste.xjtu.edu.cn/index.do*

![02](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/02.jpg)

### 问题2. 在评价页面点击“提交”按钮后，提示“请填写所有题目！”

问题1 解决之后，可以点击课程列表右侧的“填表”进行课程评教。

![03](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/03.jpg)

但是，在填写完“全部”评价项后，点击“提交”按钮，会出现“请填写所有题目”的提示。

![04](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/04.jpg)

**规避方案：**
1. 在上图的网页，按键盘右上角的F12，打开浏览器控制台(Console)
![06](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/06.jpg)
2. 在浏览器控制台中粘贴如下两行代码，敲回车，展示滚动条
```javascript
document.querySelector('.webix_window').style.position = '';
document.querySelector('.webix_layout_form').style.overflowY = 'scroll';
```
![07](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/07.jpg)
3. 点击浏览器控制台右上角的×，关闭控制台，拖动滚动条填写全部评价即可
![08](https://img.zhangchunxin.com/blog/2018-12-28-xjtu-course-evalute-system-bug-avoid/08.jpg)
