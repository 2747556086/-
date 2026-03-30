# 可交付项目合集（可售卖 / 可代部署 / 可运维）

本仓库提供两套可直接交付上线的成品系统，支持**售卖源码**、**代部署上线**、**二次开发**与**后期运维**。  
如需演示站、部署报价、功能改造清单，可按文末联系方式沟通。

---

## 1) 智慧社区物业系统（缴费 / 报修 / 便民商城）

### 技术栈
- **后端**：Java 21（JDK 21+）、Spring Boot 3.2.x、Spring Security + JWT（无状态认证）、MyBatis-Plus 3.5.5、MySQL 8.0、Apache POI（缴费记录导出 Excel）
- **前端**：Vue 3 + Vite 5、Vue Router + Pinia、Element Plus、Axios（请求封装、JWT 拦截器）

### 功能概览
- **居民端**  
  - 首页（轮播公告 + 九宫格入口 + 待办卡片）  
  - 报修（提交 / 进度 / 历史 / 评价）  
  - 缴费（分类展示、未缴红标、多支付方式模拟、导出 Excel）  
  - 便民购物（浏览 / 下单 / 支付 / 确认收货）  
  - 热点实事（浏览排行）、消息提醒  
  - 我的订单、草稿保存、常用收藏
- **物业端**  
  - 报修接单与状态更新  
  - 缴费确认  
  - 与居民端接口复用，通过角色区分
- **管理员端**  
  - 数据看板（报修完成率、缴费率、订单量…）  
  - 用户管理（列表 / 状态 / 重置密码 / 新增居民物业账号）  
  - 公告管理、热点管理、商品管理  
  - 报修超时提醒列表

### 权限与安全
- **RBAC**：角色 `RESIDENT / PROPERTY / ADMIN`，接口使用 `@PreAuthorize("hasRole('ADMIN')")` 等控制  
- **前后端双重鉴权**：后端校验 JWT + 角色；前端路由守卫按角色跳转  
- **密码安全**：BCrypt 存储；登录支持验证码（模拟模式）；连续失败锁定账号（次数/时长可配置）  
- **JWT**：登录态令牌，退出即时失效

---

## 2) 在线招聘系统（Online Recruitment System）

### 技术栈
- **后端**：Spring Boot 3.x、MyBatis Plus、Spring Security、JWT、MySQL 8.0
- **前端**：Vue 3（Composition API）、Element Plus、Pinia、Vite
- **富文本**：WangEditor（Vue 3）
- **文件存储**：本地 `uploads` 目录（可替换为 MinIO）

### 项目结构（示例）
- `backend/`：Spring Boot 后端（controller/service/mapper/security 等）
- `frontend/`：Vue3 前端（api/router/stores/views 等）
- `backend/src/main/resources/db/schema.sql`：建表脚本
- `backend/src/main/resources/application.yml`：数据库连接等配置

### 数据库快速开始
1. **创建数据库并执行脚本**  
   - 可直接执行：`backend/src/main/resources/db/schema.sql`
2. **修改配置**  
   - 在 `backend/src/main/resources/application.yml` 中配置 `spring.datasource.url/username/password`
3. **启动后端后自动创建默认管理员**  
   - **默认管理员**：`admin / admin123`

### 已实现功能（摘要）
- Spring Boot + MyBatis Plus + Spring Security + JWT + BCrypt
- 登录注册、权限与路由控制
- 富文本发布（WangEditor）、图片上传（本地 `uploads`）
- 业务模块（按项目实现：企业端/求职端/管理员端）支持扩展与二开

---

## 交付与服务（售卖 / 上线 / 运维）
- **交付方式**：源码交付 / 打包部署（JAR + 前端静态站）/ Docker 化（可选）/ 文档 + 视频教程（可选）
- **部署支持**：Windows / Linux 服务器、域名与 HTTPS、Nginx 反代、MySQL 安装与备份策略
- **二次开发**：按需求评估（UI 换肤、字段扩展、第三方支付/短信、权限细化、报表导出等）
- **售后运维**：Bug 修复、版本升级、安全加固、数据迁移、性能优化

---

## 联系与合作
- **合作内容**：购买成品系统 / 毕设项目（代做/辅导/答辩）/ 企业外包开发
- **交付周期**：按需求评估（可加急）
- **对接方式**：请提供你的联系方式与偏好沟通渠道（微信/QQ/电话/邮箱），我会把演示与报价单整理给你

