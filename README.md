# Auth Matrix

> 企业级权限管理系统 - 基于RBAC1.0的前后端分离解决方案

[![Backend](https://img.shields.io/badge/Backend-Spring%20Boot%203.5.3-brightgreen)](https://github.com/thirty30ww/auth-matrix-backend)
[![Frontend](https://img.shields.io/badge/Frontend-Vue%203.5.17-blue)](https://github.com/thirty30ww/auth-matrix-frontend)
[![Java](https://img.shields.io/badge/Java-17-orange)](https://openjdk.java.net/)
[![License](https://img.shields.io/badge/License-MIT-blue)](LICENSE)

## 项目简介

Auth Matrix 是一套完整的企业级权限管理系统，采用前后端分离架构，实现了基于RBAC1.0（Role-Based Access Control）的权限控制模型。系统支持用户管理、角色分配、菜单权限配置、操作日志审计等核心功能，适用于中小型企业的权限管理需求。

### 技术栈

**后端技术**
- Spring Boot 3.5.3 + Spring Security 6.x
- MyBatis Plus 3.5.7 + Dynamic Datasource
- MySQL 8.0 + Redis 6.0
- JWT 0.11.5 认证

**前端技术**
- Vue 3.5.17 + TypeScript 5.8.3
- Element Plus 2.10.4 + Pinia 3.0.3
- Vite 7.0.4 + Vue Router 4.5.1
- Axios 1.10.0

## 项目结构

本仓库为元仓库（Meta Repository），包含前后端子模块：

```
auth-matrix/
├── backend/          # 后端服务 - Spring Boot 3 + MyBatis Plus
├── frontend/         # 前端界面 - Vue 3 + Element Plus
└── version/          # 版本更新日志
```

- **后端服务**: [Auth Matrix Backend](https://github.com/thirty30ww/auth-matrix-backend)
- **前端界面**: [Auth Matrix Frontend](https://github.com/thirty30ww/auth-matrix-frontend)

## 快速开始

> [!IMPORTANT]
> 必须使用 `--recursive` 参数克隆子模块

```bash
# SSH 方式
git clone --recursive git@github.com:thirty30ww/auth-matrix.git

# HTTPS 方式
git clone --recursive https://github.com/thirty30ww/auth-matrix.git
```

已克隆但缺少子模块：
```bash
git submodule update --init --recursive
```

## 部署指南

1. **后端部署**: 参考 [backend/document](backend/document/)
2. **前端部署**: 参考 [frontend/document](frontend/document/)

## 默认账号

| 用户名 | 密码 | 角色 |
|--------|------|------|
| 100001 | Am20250914 | 超级管理员 |

> [!WARNING]
> 生产环境请立即修改默认密码

## 核心功能

### 系统仪表盘
- 用户统计数据可视化
- 系统运行状态监控
- 数据趋势图表展示
- 公告通知管理

### 用户管理
- 用户信息的增删改查
- 批量操作（启用/禁用/删除）
- 用户角色分配
- 密码重置

### 角色管理
- 角色层次体系（RBAC1.0）
- 角色权限分配
- 角色继承机制
- 权限预览

### 菜单管理
- 树形菜单结构
- 四级权限粒度（目录→菜单→页面→按钮）
- 权限码配置
- 图标选择器

### 日志审计
- 登录日志记录
- 操作日志追踪
- 日志查询与导出

## 系统架构

### 后端架构

```
backend/
├── am-core          # 核心启动模块 - 统一配置与服务编排
├── am-user          # 用户权限模块 - RBAC核心实现
├── am-system        # 系统管理模块 - 配置与日志管理
├── am-common        # 通用组件模块 - 共享工具与枚举
├── sql/             # 数据库脚本 - 自动化部署脚本
└── document/        # 详细文档 - 分步部署指南
```

**核心特性**
- AOP自动数据源切换
- 双数据库分离设计（user/system）
- 模块化Maven架构
- JWT无状态认证

### 前端架构

```
frontend/
├── src/
│   ├── assets/      # 静态资源 - 图标、样式、主题
│   ├── components/  # 组件库 - 业务组件与基础组件
│   ├── layouts/     # 布局系统 - Header/Sidebar双模式
│   ├── router/      # 路由管理 - 动态路由与权限守卫
│   ├── stores/      # 状态管理 - Pinia模块化状态
│   ├── services/    # API服务 - HTTP请求与接口定义
│   ├── views/       # 页面视图 - 业务功能页面
│   └── types/       # 类型定义 - TypeScript类型系统
└── document/        # 详细文档
```

**核心特性**
- 动态路由加载
- 权限指令系统（v-permission）
- 双主题切换（明暗模式）
- TypeScript全覆盖

## 系统截图

> [!NOTE]
> 以下截图展示了系统的主要功能界面

### 系统仪表盘

![image-20251229162718357](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162718357.png)

*数据统计、图表展示、系统监控*

### 用户管理

![image-20251229162733523](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162733523.png)

*用户列表、筛选、批量操作*

### 角色管理

![image-20251229162746239](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162746239.png)

*角色层次结构、权限分配*

### 菜单管理

![image-20251229162756495](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162756495.png)

![image-20251229162811267](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162811267.png)
*菜单树配置、权限码设置*

### 个人设置

![image-20251229162831895](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162831895.png)

![image-20251229162850264](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162850264.png)

![image-20251229162903581](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162903581.png)

![image-20251229162951486](https://thirty30ww.oss-cn-hangzhou.aliyuncs.com/hosting/image-20251229162951486.png)

*主题定制、个人资料、安全设置*

## 贡献指南

欢迎提交 Issue 和 Pull Request 来帮助改进项目。

## 开源协议

本项目基于 [MIT](LICENSE) 协议开源，支持商业使用和二次开发。

## 相关链接

- 后端仓库: [Auth Matrix Backend](https://github.com/thirty30ww/auth-matrix-backend)
- 前端仓库: [Auth Matrix Frontend](https://github.com/thirty30ww/auth-matrix-frontend)
- 问题反馈: [Issues](https://github.com/thirty30ww/auth-matrix/issues)

---

如果这个项目对你有帮助，欢迎给个 Star 支持一下