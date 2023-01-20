# 服务端

服务端项目 `metalflow` 采用 `Gin + GORM + JWT + Casbin` 组合实现完成。是一款 `RESTful` 风格的 `RBAC` 权限管理系统。



## 特性

- **RESTful API** 设计风格
- **Gin** 一款高效的 Go web 框架
- **JWT** 用户认证
- **MySQL** 数据库存储
- **Casbin** 基于角色的访问控制模型（RBAC）
- **GORM** 数据库 ORM 管理框架
- **Validator** 请求参数校验 版本 v9
- **Lumberjack** 日志切割工具，高效分离大日志文件，按日期保存文件
- **Viper** 配置管理工具，支持多种配置文件类型
- **Machinery** Go 异步任务调度框架
- **WebSockets** Go WebSockets 协议工具库
- **gRPC** 谷歌开源的 RPC 框架



## 中间件

- **Exception** 全局异常处理中间件 -- 使用 Go recover 特性, 捕获所有异常, 保存到日志, 方便追溯
- **Transaction** 全局事务处理中间件 -- 每次请求无异常自动提交, 有异常自动回滚事务, 无需每个 service 单独调用（GET/OPTIONS 跳过）
- **AccessLog** 请求日志中间件 -- 每次请求的路由自动写入日志
- **CORS** 跨域中间件 -- 所有请求均可跨域访问
- **JWTAuth** 权限认证中间件 -- 处理登录、登出、无状态 token 校验
- **CasbinMiddleware** 权限访问中间件 -- 基于 Casbin RBAC, 对不同角色访问不同 API 进行校验


## 目录

```
├─api
│  └─v1  # v1 版本接口目录
├─doc # API 文档目录
│  └─html
│      └─assets
├─initialize # 数据初始化目录
│  └─conf # 初始化配置文件目录
├─logs # 日志文件目录（代码运行后产生）
├─middleware # 中间件目录
├─models # 存储层模型定义目录
├─pkg # 公共模块目录
│  ├─async # 异步任务工具目录
│  ├─consul # consul 连接工具目录
│  ├─cron # 定时任务工具目录
│  ├─global # 全局变量目录
│  ├─grpc # gRPC 服务相关目录
│  │  ├─pb
│  │  ├─securepb
│  │  ├─tunepb
│  │  └─uploadpb
│  ├─request # 请求体的结构目录
│  ├─response # 响应体的结构目录
│  ├─service # 数据 DAO 服务目录
│  │  └─script # 内嵌的脚本文件目录
│  ├─utils # 工具包目录
│  └─vncproxy # VNC 连接工具目录
├─router # 路由目录
├─tests # 测试相关配置目录
│─upload # 上传文件默认目录（代码运行上传文件时产生）
│——go.mod # Go 依赖列表
│——go.sum # Go 依赖下载历史
│——main.go # 程序主入口
|——README.md # 说明文档
```
