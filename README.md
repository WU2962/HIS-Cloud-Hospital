

# 东软云医院HIS系统

## 项目简介

东软云医院HIS（Hospital Information System）系统是一套完整的医院信息管理解决方案，集成了临床诊疗、药品管理、经济管理、综合管理与统计分析等核心业务功能。系统采用现代化的前后端分离架构，能够有效支撑医院的日常运营管理需求。

## 功能特性

### 临床诊疗模块
- **门诊医生工作站**：支持病人接诊、病历书写、医嘱开立等功能
- **住院医生工作站**：提供住院病人管理、诊疗计划制定等服务
- **护士工作站**：护理记录执行、医嘱核对等护理工作支持
- **检验系统**：检验申请、样本管理、结果录入等检验流程管理
- **检查系统**：检查预约、报告生成、影像资料管理等

### 药品管理模块
- 药品库存管理、入库出库管理
- 药房发药管理
- 合理用药审核与用药咨询服务

### 挂号收费模块
- 门诊挂号管理与号源控制
- 费用计算与收费管理
- 退费处理与发票管理
- 挂号退号管理

### 系统管理模块
- 用户管理与权限控制
- 角色权限分配
- 科室信息管理
- 常量数据维护

## 技术栈

### 后端技术
- **框架**：Spring Boot 2.x
- **ORM框架**：MyBatis-Plus
- **认证授权**：JWT（JSON Web Token）
- **日志处理**：SLF4J
- **数据库**：MySQL 5.7+/8.0+

### 前端技术
- **框架**：Vue.js 2.x
- **状态管理**：Vuex
- **UI组件库**：Element UI
- **HTTP客户端**：Axios
- **路由管理**：Vue Router

## 项目结构

```
his/
├── src/main/java/com/antrain/his/
│   ├── annotation/           # 自定义注解
│   │   ├── PassToken.java   # 跳过Token验证注解
│   │   └── UserLoginToken.java  # 需要登录Token注解
│   ├── config/              # 配置类
│   │   ├── CrossConfig.java      # 跨域配置
│   │   ├── DefaultFastjsonConfig.java  # JSON配置
│   │   ├── InterceptorConfig.java     # 拦截器配置
│   │   └── MybatisPlusConfig.java     # MyBatis-Plus配置
│   ├── controller/          # 控制器层
│   │   ├── LoginController.java       # 登录认证
│   │   ├── UserController.java        # 用户管理
│   │   ├── RoleController.java        # 角色管理
│   │   ├── PermissionController.java  # 权限管理
│   │   ├── DepartmentController.java  # 科室管理
│   │   ├── RegisterController.java    # 挂号管理
│   │   ├── CheckApplyController.java  # 检查申请
│   │   ├── CheckItemController.java   # 检查项目
│   │   ├── InspectApplyController.java # 检验申请
│   │   ├── InspectItemController.java  # 检验项目
│   │   ├── ConstantTypeController.java # 常量类型
│   │   ├── ConstantItemController.java # 常量项目
│   │   ├── RegistLevelController.java  # 挂号级别
│   │   ├── RolePermissionController.java # 角色权限
│   │   └── UserRoleController.java      # 用户角色
│   ├── entity/              # 实体类
│   │   ├── User.java        # 用户实体
│   │   ├── Role.java        # 角色实体
│   │   ├── Permission.java  # 权限实体
│   │   ├── Department.java  # 科室实体
│   │   ├── Register.java    # 挂号实体
│   │   ├── CheckApply.java  # 检查申请实体
│   │   ├── InspectApply.java # 检验申请实体
│   │   ├── CheckItem.java   # 检查项目实体
│   │   ├── InspectItem.java # 检验项目实体
│   │   ├── ConstantType.java # 常量类型实体
│   │   ├── ConstantItem.java # 常量项目实体
│   │   ├── RegistLevel.java  # 挂号级别实体
│   │   ├── RolePermission.java # 角色权限实体
│   │   └── UserRole.java     # 用户角色实体
│   ├── service/             # 服务层接口
│   │   └── impl/            # 服务实现类
│   ├── mapper/              # 数据访问层
│   │   └── xml/             # Mapper XML文件
│   ├── handler/             # 处理器
│   │   ├── AuthenticationInterceptor.java  # 认证拦截器
│   │   └── GlobalExceptionHandle.java      # 全局异常处理
│   ├── exception/           # 异常类
│   │   ├── MyException.java
│   │   ├── NotAuthorityException.java
│   │   ├── NotExistException.java
│   │   └── UserNoLoginException.java
│   └── utils/               # 工具类
│       ├── JwtUtil.java     # JWT工具
│       ├── Result.java      # 统一响应结果
│       ├── ResultGenerator.java  # 结果生成器
│       ├── Constants.java   # 常量定义
│       ├── InitUtil.java    # 初始化工具
│       ├── CodeGenerator.java  # 代码生成器
│       └── ShaUtil.java     # SHA加密工具
│
└── src/main/resources/
    └── application.yml      # 应用配置

his-vue/
├── public/
│   └── index.html
├── src/
│   ├── main.js             # 应用入口
│   ├── App.vue             # 根组件
│   ├── router/index.js     # 路由配置
│   ├── store/              # Vuex状态管理
│   ├── views/              # 页面组件
│   │   ├── Login.vue       # 登录页面
│   │   ├── Home.vue        # 首页
│   │   ├── user/           # 用户管理
│   │   ├── role/           # 角色管理
│   │   ├── permission/     # 权限管理
│   │   ├── department/     # 科室管理
│   │   ├── doctor/         # 医生管理
│   │   ├── register/       # 挂号管理
│   │   ├── registlevel/    # 挂号级别
│   │   ├── check-item/     # 检查项目
│   │   ├── inspect-item/   # 检验项目
│   │   ├── constant-type/  # 常量类型
│   │   └── constant-item/  # 常量项目
│   ├── components/         # 公共组件
│   ├── assets/             # 静态资源
│   └── utils/              # 前端工具类
│       └── axiosUtil.js    # Axios封装
└── package.json
```

## 快速开始

### 环境要求

- JDK 11（pom.xml 指定 Java 11；JDK 8 或 21 无法直接编译运行）
- Node.js 12.0+（Node 17+ 启动前端需先设置 `NODE_OPTIONS=--openssl-legacy-provider`）
- MySQL 5.7+
- Maven 3.6+

### 数据库配置

1. 创建数据库：`CREATE DATABASE his DEFAULT CHARACTER SET utf8mb4;`
2. 导入数据库脚本：`doc-sql/his.sql`

### 后端配置

1. 使用IDE导入项目 `his`
2. 执行 `mvn dependency:resolve` 下载依赖
3. 修改 `src/main/resources/application.yml` 中的数据库连接配置：
   ```yaml
   spring:
     datasource:
       url: jdbc:mysql://localhost:3306/his?useUnicode=true&characterEncoding=utf8&useSSL=false&serverTimezone=Asia/Shanghai
       username: your_username
       password: your_password
   ```
4. 运行 `WebApp.java` 中的 `main` 方法启动后端服务（端口 8088）

> 注意：`application.yml` 中默认数据库密码为 `123456`，请改成你本机 MySQL 的密码后再启动。

### 前端配置

1. 使用VS Code打开项目 `his-vue`
2. 安装依赖：
   ```bash
   npm install
   ```
3. 配置API地址（如有需要）：后端地址在 `src/utils/axiosUtil.js` 的 `baseURL`（默认 `http://127.0.0.1:8088`）。局域网内其他电脑访问时，请改成你电脑的局域网 IP
4. 启动开发服务器：
   ```bash
   npm run serve
   ```
   > Node 17+ 需先设置环境变量再启动：
   > - cmd：`set NODE_OPTIONS=--openssl-legacy-provider`
   > - PowerShell：`$env:NODE_OPTIONS="--openssl-legacy-provider"`

### 访问系统

- 打开浏览器访问前端：`http://localhost:8080/`（若 8080 被占用，以 npm 控制台实际提示的端口为准）
- 后端服务地址：`http://127.0.0.1:8088`
- 登录使用**手机号 + 密码**：
  - 超级管理员：`18905621669` / `admin`
  - 其他用户默认密码：`123456`（如 华佗：`15305560455` / `123456`）

### 局域网访问（同一网络内的其他设备）

用于课堂演示/答辩，访客设备无需安装任何环境：

1. 前端 API 地址已配置为自动跟随页面地址（`src/utils/axiosUtil.js` 中 `baseURL` 动态取 `window.location.hostname`），无需修改
2. Windows 防火墙需放行 8081、8088 两个端口（管理员身份运行）：
   ```bat
   netsh advfirewall firewall add rule name="HIS-Hospital-8081" dir=in action=allow protocol=TCP localport=8081
   netsh advfirewall firewall add rule name="HIS-Hospital-8088" dir=in action=allow protocol=TCP localport=8088
   ```
3. 命令行运行 `ipconfig` 查询本机局域网 IP
4. 访客与本机连接同一网络（校园网/同一 WiFi），浏览器打开 `http://<你的IP>:8081` 即可
5. 注意：换网络后 IP 会变化，访客需改用新 IP 访问，代码无需改动；若同一网络下仍无法互访，可能是路由器开启了 AP 隔离，可改用手机热点

## API接口说明

### 认证接口

| 方法 | 路径 | 说明 | 权限 |
|------|------|------|------|
| POST | /login | 用户登录 | 公开 |

### 系统管理接口

| 方法 | 路径 | 说明 | 权限 |
|------|------|------|------|
| GET | /users | 获取用户列表 | @UserLoginToken |
| POST | /users | 创建用户 | @UserLoginToken |
| PUT | /users/{id} | 更新用户 | @UserLoginToken |
| DELETE | /users/{id} | 删除用户 | @UserLoginToken |
| GET | /roles | 获取角色列表 | 公开 |
| POST | /roles | 创建角色 | @UserLoginToken |
| PUT | /roles/{id} | 更新角色 | @UserLoginToken |
| GET | /permissions | 获取权限列表 | 公开 |
| POST | /permissions | 创建权限 | @UserLoginToken |
| GET | /permissions/lists | 获取权限树形结构 | @UserLoginToken |

### 业务管理接口

| 方法 | 路径 | 说明 | 权限 |
|------|------|------|------|
| GET | /departments | 获取科室列表 | 公开 |
| POST | /departments | 创建科室 | @UserLoginToken |
| PUT | /departments/{id} | 更新科室 | @UserLoginToken |
| GET | /registers | 获取挂号列表 | @UserLoginToken |
| POST | /registers | 创建挂号 | @UserLoginToken |
| PUT | /registers/receive/{id} | 接收挂号 | @UserLoginToken |
| PUT | /registers/num/{id} | 退号 | @UserLoginToken |
| GET | /checkItems | 获取检查项目列表 | 公开 |
| POST | /checkItems | 创建检查项目 | @UserLoginToken |
| GET | /checkApplys | 获取检查申请列表 | 公开 |
| POST | /checkApplys | 创建检查申请 | @UserLoginToken |
| PUT | /checkApplys/fee | 缴费 | @UserLoginToken |
| PUT | /checkApplys/refund | 退费 | @UserLoginToken |
| GET | /inspectItems | 获取检验项目列表 | 公开 |
| POST | /inspectItems | 创建检验项目 | @UserLoginToken |
| GET | /inspectApplys | 获取检验申请列表 | 公开 |
| POST | /inspectApplys | 创建检验申请 | @UserLoginToken |
| GET | /constantTypes | 获取常量类型列表 | 公开 |
| POST | /constantTypes | 创建常量类型 | @UserLoginToken |
| GET | /constantItems | 获取常量项目列表 | 公开 |
| POST | /constantItems | 创建常量项目 | @UserLoginToken |
| GET | /registLevels | 获取挂号级别列表 | 公开 |
| POST | /registLevels | 创建挂号级别 | @UserLoginToken |

## 认证机制

系统采用JWT（JSON Web Token）进行用户认证。

### Token获取

用户通过 `/login` 接口登录，成功后返回JWT Token。

### Token使用

客户端在请求头中携带Token：
```
Authorization: Bearer <your_jwt_token>
```

### 注解说明

- `@PassToken`：标记的接口无需验证Token
- `@UserLoginToken`：标记的接口需要验证用户Token

## 目录说明

| 目录/文件 | 说明 |
|-----------|------|
| doc-sql/his.sql | 数据库初始化脚本 |
| his-vue/src/views | 页面组件 |
| his-vue/src/components | 公共组件 |
| his-vue/src/store | Vuex状态管理 |
| his-vue/src/router | 路由配置 |
| his-vue/src/utils | 工具函数 |
| his/src/main/java/com/antrain/his/controller | 控制器 |
| his/src/main/java/com/antrain/his/service | 业务逻辑 |
| his/src/main/java/com/antrain/his/mapper | 数据访问 |
| his/src/main/java/com/antrain/his/entity | 实体类 |
| his/src/main/java/com/antrain/his/utils | 工具类 |

## License

本项目仅供学习研究使用。