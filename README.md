# 智慧养老管理平台（中州养老）

基于 **RuoYi-Vue3** 二次开发的养老机构数字化管理系统：管理后台覆盖护理等级、护理计划、护理服务管理三大业务模块，配套微信小程序（家属端）与 AI 知识问答助手。

## 业务模块

| 模块 | 说明 |
| --- | --- |
| 护理等级 | 护理级别维护、查询与启用/禁用 |
| 护理计划 | 护理计划定义，关联护理项目与执行周期 |
| 护理服务管理 | 护理服务项目维护与管理 |

## 端与功能

- **管理后台**（基于 RuoYi-Vue3）：RBAC 权限控制（菜单 / 按钮级）、业务模块 CRUD 由代码生成器低代码生成
- **微信小程序**（uni-app，源码见 `miniprogram/`）：家属绑定、服务预约下单、在线支付、健康数据图表、探访预约、账单 / 合同等 20+ 页面
- **AI 问答助手**：基于 Dify 搭建养老知识库（文档分段 + 向量检索），支持多轮对话

## 技术栈

- 后端：Spring Boot · Spring Security + JWT · MyBatis · Druid · MySQL · Redis
- 管理端：Vue3 · Element Plus · Vite（RuoYi-Vue3）
- 小程序端：uni-app（微信小程序）

## 目录结构

```
zzyl/
├── zzyl-admin/               # 启动模块（配置、控制器入口）
├── zzyl-framework/           # 框架核心（安全、数据源、AOP）
├── zzyl-system/              # 系统管理（用户、角色、菜单等）
├── zzyl-quartz/              # 定时任务
├── zzyl-generator/           # 代码生成器（低代码）
├── zzyl-nursing-platform/    # 护理业务模块（护理等级 / 护理计划 / 护理服务）
├── miniprogram/              # 微信小程序（uni-app）
├── sql/                      # 数据库脚本
└── doc/                      # 项目文档
```

## 快速开始

1. 创建数据库并导入 `sql/` 下的脚本
2. 修改 `zzyl-admin/src/main/resources/application-druid.yml` 中的数据库连接
3. 编译启动后端：
   ```bash
   mvn clean package
   java -jar zzyl-admin/target/zzyl-admin.jar
   ```
   或直接执行 `ry.bat`
4. 管理端前端使用 RuoYi-Vue3（独立前端工程）
5. 小程序端：使用微信开发者工具打开 `miniprogram/` 目录

## 说明

本项目基于开源项目 [RuoYi-Vue](https://gitee.com/y_project/RuoYi-Vue)（v3.9.2，MIT License）二次开发，原框架自带功能（用户 / 角色 / 菜单 / 定时任务 / 代码生成等）归 RuoYi 所有。
