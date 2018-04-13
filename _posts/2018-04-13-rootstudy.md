---
layout: post
title: "Vue项目结构"
date: 2018-04-03
description: "Vue项目目录结构解析"
tag: VUE笔记 
--- 
### Vue新建一个项目的根目录结构
 ```

├── build       # 一些webpack的文件，配置参数什么的，一般不用动 
├── config      # vue项目的基本配置文件 
├── index.html       # 主页
├── node_modules     # 项目中安装的依赖模块 
├── package.json     # 项目文件，记载着一些命令和依赖还有简要的项目描述信息 
├── README.md 
├── server           # 自己创建的后端文件，可以忽视
├── src              # 源码文件夹，基本上文件都应该放在这里
  ├── App.vue        # App.vue组件 <br>
  ├── assets         # 资源文件夹，里面放一些静态资源 
  ├── components     # 这里放的都是各个组件文件 
  ├── main.js        # 入口文件 
  └── router         # vue-router 路由配置
├── static           # 生成好的文件会放在这个目录下
├── test             # 测试文件夹，测试都写在这里
├── .babelrc         # babel编译参数，vue开发需要babel编译 
├── .gitignore 
└── .eslintignore
├── .eslintrc.js     #代码风格规则，代码的风格定义在这
```
