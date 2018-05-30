---
layout:     post
title:      "利用@angular/cli V6.0来直接开发PWA应用了"
subtitle:   "利用@angular/cli V6.0来直接开发PWA应用"
date:       2018-05-24 12:00:00
author:     "dali"
header-img: "img/post-bg-nextgen-web-pwa.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 前端开发
    - angular
    - PWA
---

Angular正式发布了V6.0，我们已经可以利用对应的@angular/cli V6.0来直接开发PWA应用了。<br>
第一步：安装@angular/cli V6.0<br>
如果你机器上有老版本，请先卸载。<br>
打开你的终端，执行：<br>
npm install -g @angular/cli<br>
安装成功之后用ng -v 查看一下版本号：<br>
0_1525511943942_1.png
第二步：new一个空项目<br>
执行：
ng new test-ng-pwa
创建成功之后把项目起来看一下，执行：<br>
ng serve --open
浏览器里面看到这个界面说明一切OK：<br>
![](/img/in-post/post-nextgen-web-pwa/flipkart-2.jpeg)
0_1525512173369_5.png
第三步：添加PWA支持<br>
把项目停掉，然后在终端里面执行：<br>
ng add @angular/pwa
效果如下：<br>
0_1525512049594_2.png
因为@angular/cli内置的Server在--prod 编译的时候还不支持service-worker，所以上面装了一个第三方的lite-server，它的官方文档在这里：https://npmjs.com/package/lite-server ，请执行：<br>
npm install lite-server --save-dev
npm install lite-server --global
装完之后，执行：<br>
npx ng build --prod && lite-server --baseDir dist/test-ng-pwa<br>
然后打开你的浏览器访问3000端口，可以看到service-worker已经起成功了：<br>
0_1525512597244_3.png
0_1525512579997_6.png
这时候你已经可以把应用添加到桌面上了：<br>
0_1525512634683_4.png
这是Windows上的效果：<br>
0_1525512744332_7.png
Linux、iOS、Android、ChromeOS最新的版本都已经全部支持，你自己去试试吧！
