---
layout:     post
title:      "Angular中为什么要有router"
subtitle:   "router"
date:       2018-12-2 23:10:00
author:     "dali"
header-img: "img/post-bg-nextgen-web-pwa.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 前端开发
    - Angular
    - router
---

### Angular静态同步路由和异步路由

- NgModule 为什么需要NgModule
- 默认加到模块这一层 
- 每次路径需要规划好,在哪个业务模块下做几层路由，几级结构，参数是什么样的。 
![route](/../img/router-tree.jpg)  
- 静态路由
- 异步路由

```TS
import {RouterModule}from'@angular/router';  
import {HomeComponet} from './homecomponet';  
const homeRouter =[  
    {path:'',component:HomeCompoent}  
];  
export default RouterModule.forChild(homeRoutes)  
```
### 异步路由
```TS
import {RouterModule} from '@angular/router'
const Routers=[
    {
        path:'',
    loadChildren:'app/home/home.module'},
     {
        path:'home',
    loadChildren:'app/home/.home.module'},
     {
        path:'user',
    loadChildren:'app/user/user.module'},
     {
        path:'role',
    loadChildren:'app/home/role.module'},

]

export default RouterModule.forChild(homeRoutes)
```
