# 前端

前端项目 `metalweb` 采用 [Vue.js](https://cn.vuejs.org/guide/introduction.html) 和 [Ant Design Vue](https://antdv.com/components/overview-cn) 等技术栈。
其基于成熟的前端集成框架 [Vue-Vben-Admin](https://jacobhsu.github.io/vue-vben-admin-docs/guide/introduction.html)（一款基于 Vue3.0、Vite、 Ant-Design-Vue、TypeScript 的后台解决方案）进行二次开发。



## 目录

```
├─build
├─mock  # 用于随机生成数据测试页面功能
├─node_modules # 依赖包（下载依赖包时生成）
├─public # 公共资源，存放站点图标等
├─src      # 代码主目录
│  ├─api    # 请求后端的api
│  ├─assets  # 图片资源
│  ├─components # 公共的vue组件
│  ├─design
│  ├─directives
│  ├─enums
│  ├─hooks
│  ├─layouts # 网站主页面的组件
│  ├─locales
│  ├─logics
│  ├─router  # 网站路由
│  ├─settings
│  ├─store  # 网站全局的状态数据
│  ├─utils # 相关工具代码（用户认证、请求内容过滤设置、数据校验等）
│  └─views # 网站页面存放处
│      ├─back # 后台管理相关页面存放处
│      ├─dashboard # 首页页面存放处
│      ├─node # 服务器列表等页面存放处
│      └─sys # 系统管理相关页面存放处
├─tests  # 测试相关
|─types
│  .env   # 环境变量
│  .env.development # 开发时环境变量配置
│  .env.production  # 生产环境变量配置
│  .env.test  # 测试环境变量配置
│  package.json # 包依赖列表
│  README.md
│  vite.config.ts # vite相关配置
```



## 运行

在 `metalweb` 目录下，运行如下命令：

```bash
yarn install
yarn run serve
```

之后在本地访问 `http://localhost:3100/` 即可。

> 注意： 本地环境需安装 [Node](https://nodejs.org/en/) 和 [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable)。
