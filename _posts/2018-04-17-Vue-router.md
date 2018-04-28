---
layout: post
title: "Vue路由"
date: 2018-04-03
description: "Vue路由浅析"
tag: VUE笔记 
--- 
 
 #### 前言
 在学Vue之后，我们都知道Vue-router的重要性，所以我们也需要特意去深度学习它，现在我就写写我的学习笔记<br>
 
 ### 正文
 vue-router是Vue.js官方的路由插件，它和vue.js是深度集成的，适合用于构建单页面应用。vue的单页面应用是基于路由和组件的，路由用于设定访问路径，并将路径和
 组件映射起来。传统的页面应用，是用一些超链接来实现页面切换和跳转的。在vue-router单页面应用中，则是路径之间的切换，也就是组件的切换。<br>
 使用 Vue.js ，我们已经可以通过组合组件来组成应用程序，当你要把 vue-router 添加进来，我们需要做的是，将组件(components)映射到路由(routes)，然后告诉
 vue-router 在哪里渲染它们。
 #### 一、快速入门（ 所有的测试都是基于脚手架进行的，在创建项目的时候选择安装路由）
 
 ##### 1、新建组件
 在建立好的项目中新建一个组件，命名为routerA,再新建一个路由命名为routerB。建立好之后，先在main.js中引入
  1）在main.js引入方式：
 ```

 import router from ‘vue-router’
 Vue .use(VueRouter)

 ```
  2）引入之后，我们到router下的文件夹下打开index.js
 ```
 将路由配置好，配置如下
 引入：
 import RouterA from '@/components/routerA'
 import RouterB from '@/components/routerB'
 
 
 export default new Router({
  routes: [
    {
      path: '/',
      name: 'routerA',
      component: RouterA
    },
    {
      path: '/routerB',
      name: 'routerB',
      component: RouterB
    }
  ]
})

 ```
 3）现在我们启动项目之后就会在浏览器看到的首先的是routerA组件的内容，之前的默认的内容已经更换成了routerA的内容，看到这里是不是觉得这关于路由什么关系了<br><br>
 现在我们将实现最简单的路由切换：<br>
 使用：<router-link>  //组件支持用户在具有路由功能的组件中导航，通过to  的属性指定目标地址  直接点击可以跳转
 ```
 在routerA写下
 
 <router-link to="/routerB">routerB</router-link>
 
 我们可以点击它可以进入到routerB组件中。
 
 在routerB也可以这样写，这样就组件之间切换了
 
 <router-link to="/">routerA</router-link>

 ```
 
 4)我们也可以使用to绑定数据或者另一方式进行路由切换，做法如下：
 ```
 在data中的return写下如下的：
 
  urld: {
	   routerb: '/routerB'
    
    然后在视图写法如下：
    <router-link :to="urld.routerb">routerA</router-link>
    （:to是v-bind:to的简写）
 ```
 这样的写法也可以实现路由的切换，但是:to却是可以绑定数据进行传递
 
 5）:to传递数据
 路由传递参数：params, 接收参数：route.params.id
 ```
 先在组件routerA中的视图区域写下：
 <router-link :to="{name:'routerB', params:{count: 100}}">routerB</router-link>
 
 count是定义的id
 
 在routerB组件中接收参数，所以name：'routerB',具体写法如下：
 {{ $route.params.count }}
 打开浏览器切换到routerB我们会看到100，说明成功传递数据
 ```
 效果如下：<br>
 ![](/images/posts/router1.png) <br>
 未完续......
 
