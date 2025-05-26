# sky_take_out

## 项目介绍
```
功能架构：体现项目中的业务功能模块
```
### 管理端
```
员工管理    分类管理    菜品管理    套餐管理
订单管理    工作台      数据统计    来单提醒
```
### 用户端
```
微信登录    商品浏览    购物车      用户下单
微信支付    历史订单    地址管理    用户催单
```

## 技术选型

```
技术选型：展示项目中使用到的技术框架和中间件等
```
### 用户层
```
node.js    Vue.js     ElementUI    微信小程序   apache echarts       
```
### 网关层
```
Nginx
```
### 应用层
```
Spring Boot            Spring MVC       Spring Cache       
Spring Task            httpclient           JWT
阿里云OSS               Swagger
POI                     WebSocket

```
### 数据层
```
MySQL      Redis        mybatis     pagehelper
spring data redis
```
### 工具
```
git        maven        Junit       postman
```

## 项目架构详解
```
1. sky-take-out         maven父工程，统一管理原来版泵，聚合其他子模块
2. sky-take-out-common  公共模块，存放公共的工具类、常量类、异常类、配置类等
3. sky-take-out-mapper  持久层模块，存放实体类、VO、DTO等
4. sky-take-out-service 业务层模块，后端服务，存放配置文件、Controller、Service、Mapper等
```
### 核心组件功能
```
实体类     配置文件   拦截器   过滤器   监听器   异常处理器   日志记录   定时任务
VO        全称    Value Object            用于封装数据，用于前端展示
DTO       全称    Data Transfer Object    用于封装数据，用于后端传输  
```
```
sky-common: 子模块中存放的是一些公共类，可以共其他模板使用
  -constant: 常量类
  -context: 上下文类
  -enumeration: 枚举类
  -exception: 异常类
  -json: 处理json转换的类
  -properties: 配置SpringBoot中的属性的类
  -result: 统一返回结果的类
  -utils: 工具类  
```
```
sky-pojo:   子模块中存放的是一些entity、DTO、VO等类
  -entity:  实体类,通常和数据库中的表对应
  -vo:      视图对象，为前端提供展示数据的对象
  -dto:     数据传输对象，通常用于程序中各层之间传递数据
  -pojo:    普通的Java对象，只有属性和对应的getter和setter方法 
```

```
sky-server: 子模块中存放的是 配置文件、配置类、拦截器、Controller、Service、Mapper、启动类等
  -config:  配置类,用于配置SpringBoot中的属性
  -handler: 异常处理器,用于处理异常
  -controller.admin: 管理端Controller
  -interceptor:  拦截器,用于拦截请求,进行权限校验
  -mapper:  持久层Mapper,用于操作数据库
  -service: 业务层Service,用于处理业务逻辑
```

```
Controller: 接收前端请求，处理业务逻辑，返回响应结果
Service: 处理业务逻辑, 调用Mapper进行数据库操作
Mapper: 映射数据库表和实体类之间的关系
```

## 注意事项
```
注意事项：项目中可能遇到的问题和解决方案
1. 项目使用的是 JDK 18 版本，需要确保本地环境已经配置好 JDK 18（不高于）有人反映使用1.8版本的会报错，建议使用18版本也不会报错
2. 项目使用的是 Maven 3.8.6 版本，需要确保本地环境已经配置好 Maven 3.8.6
3. 项目使用的是 MySQL 8.0.32 版本，需要确保本地环境已经配置好 MySQL 8.0.32
4. 如果直接使用黑马程序员的架构，最好将lombok版本调为1.18.30（如果你使用的jdk低于18就不用）
5. 本地项目启动时，记得重新配置mysql的密码，具体位置在application-dev.yml文件中（application.yml是直接注入的）
```

