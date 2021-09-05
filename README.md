#ego商城后台系统
本项目是一个商城的后台系统，具有商城的商品管理、规格参数管理、广告分类管理等。
其中包含用户中心、用户登录与注册、集成国际化语言环境、支持中英文两种语言、项目采用vue技术栈

### 项目技术
1.项目环境：vue-cli构建项目，集成项目环境（前后端同步实现、集成了Node服务器、集成XAMPP）
2.项目技术点：
    -项目网络请求Axios,同时对Axios进行封装，主要处理请求拦截和相应拦截及错误信息
    -项目UI采用ElementUi,并对ElementUi进行二次封装，主要引入组件包含：table表格、tree树形控件、form表单、
    dialog弹出框等
    -项目页面直接采用Vue-Router路由管理，包含路由嵌套功能、路由导航、路由传参、路由权限管理
    -项目的全局状态、包含登录token、订单信息等采用Vuex进行管理，并跟踪数据变化
    -由于商品具有编辑功能，所有引入了富文本编辑器
    -因为项目开发是前后端同步，所以前期数据采用node+mock做数据模拟，并且在开发环境下采用props解决跨域问题
3.业务实现
    -具体业务实现...

 ## 项目心得

 ## 项目亮点

 ## 安装项目依赖
 1.安装网络请求Axios 'cnpm install --save axios'
 2.集成ElementUI组件库 'vue add element'                    Still proceed? Yes      按需加载

 ## 项目页面结构
 1.商品管理:product
 2.规格参数：params
 3.内容分类管理:Content
 4.用户登录注册页面:login
 5.用户中心:ucenter

    --login
    --layout
        --content
        --params
        --product
    --user

### 初始化css样式

## 实现登录页面:login.vue
1.用到的组件：el-card、el-tabs、el-form
2.具体功能
    1.登录
        1.完成网络请求的处理
## 实现后台服务器提供接口
Node+MySql

1.安装依赖:cnpm install --save express
mysql连接数据库:cnpm install --save mysql
## 注意  配置好后得进入到server目录下才能访问node index.js
        2.解决跨域问题
            1.前端解决：
            2.后端解决:
                cors方案:'cnpm install --save cors'
                然后在server 的index.js中加入:const cors=require("cors");
                                             //解决跨域
                                              app.use(cors());
    同时启动前后端:进入package.json中的scripts中加入:  "dev":"concurrently \"npm run serve\"  \"node server/index.js\""  ,并安装cnpm install -g concurrently,
    3.就可以运行npm run dev了
    4.node服务器自动重启 'npm install -g nodemon',并把"dev":"concurrently \"npm run serve\"  \"node server/index.js\""改成"dev":"concurrently \"npm run serve\"  \"nodemon server/index.js\""
        3注册
            1.注册时候验证
            2.网络请求的交互
            3.ElementUI组件:message

## 路由权限管理
router中的permission.js中就是配置,router中的index.js要重定向，注意！！

## 用户登录的验证
1.Vuex管理用户登录状态,在store中的index.js进行配置,创建在store下modules文件夹并创建loginModule.js
2.token用户凭证
    前端发送用户名密码 ->  后台验证用户名密码是否成功（生成token）-> 返回token用户凭证 ->前台保存的是用户凭证
    1.安装依赖 'cnpm install --save jsonwebtoken'
3.本地存储:localStorage

## 解析token值:
1.安装依赖:cnpm install --save jwt-decode
2.用户名和token存入到vuex和本地中(注意转码):JSON.stringify();
3.退出登录: 
清除本地数据和vuex的数据，路由回到登录页
this.clearToken();
localStorage.removeItem("ego");
this.$router.push("/login");


### 商品管理
1.关于联合调试
    前端和后台的联合调试
        1.字段
        2.接口地址（backend/item/...）
2.前后端开发各干各的，前端在没有拿到接口之前，只做页面UI的处理
3.使用到的ElementUI组件
    1.使用Table表格
## 分页功能
1.使用到的Element组件
    1.Pagination 分页
2.组件之间的数据交互
    1.子父级：prop  自定义事件
    2.同级组件
        1.eventbus(事件总线)
        2.vuex

### 模糊搜索功能
1.form表单阻止默认事件:@submit.native.prevent
2.监听回车事件: @keyup.enter.native='onSubmitSearch'

## 国际化处理
vue-i18n 参考地址:直接搜
安装依赖cnpm install vue-i18n --save
配合ElementUI处理语言环境
i18n是用方案和vuex与router相似

## 添加功能
1.使用到elementUI组件
    1.dialog对话框（内嵌dialog）
    2.tree树形控件（懒加载）
    3.upload上传
2.主要功能
    1.tree懒加载
    2.上传图片
    3.富文本编辑器
        1.百度富文本编辑器
        2.wangEditor
3.组件交互关系
    1.子传父：自定义事件（$emit）
    2.eventbus:同级关系的数据传递


## 删除功能

## 编辑功能
    1.父传子props

## 修改功能
1.预更新：修改数据的时候，不能从本地读取当前的数据，因为同时使用项目的不止一个人，如果别人修改了，你看到的数据是被修改之前的数据
2.wangEditor的bug:加载方式的bug,不用通过id引用，而是通过ref的形式

## 规格参数
### 规格参数添加功能
## 规格参数删除功能
## 内容分类-标题显示