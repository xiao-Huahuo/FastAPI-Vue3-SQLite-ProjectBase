# 通用FastAPI-Vue-SQLite项目README

## 项目简介
这是一个基于FastAPI、Vue 3和SQLite的全栈项目模板，旨在提供一个高效、可扩展的开发框架。后端使用FastAPI构建RESTful API，前端使用Vue 3搭建单页应用(SPA)，数据存储采用轻量级的SQLite数据库。项目结构清晰，模块化设计，适合快速开发和部署现代Web应用。
后端采用"接口层-业务层-智能层-数据层"的分层架构，确保代码的高内聚和低耦合，便于维护和扩展。
前端采用MVVM三层设计理念,将视图、数据和逻辑分离，提升代码的可读性和可维护性。使用Pinia进行状态管理，确保应用状态的一致性和可预测性。

---

## 项目文件结构  

```shell  
MetaWeave/
├── app/                        # 后端核心 (FastAPI)
│   ├── main.py                 # 【入口】FastAPI 初始化、中间件配置与路由挂载
│   ├── ai/                     # 智能中枢层
│   ├── api/                    # 接口定义层
│   │   ├── deps.py             # 【依赖】JWT 校验、DB Session 获取
│   │   └── router/             # 接口层
│   ├── core/                   # 核心配置
│   │   ├── config.py           # 【配置】环境变量读取、全局常量
│   │   ├── cors.py             # 跨域请求(CORS)中间件管理
│   │   ├── database.py         # 数据库连接配置与Session管理
│   │   ├── logger.py           # 日志记录器配置
│   │   └── security.py         # 密码哈希、Token 生成逻辑
│   ├── db/                     # 数据库业务逻辑
│   ├── models/                 # 数据模型 (SQLModel/Pydantic)
│   ├── services/               # 业务逻辑层
│   ├── requirements.txt        # Python 依赖清单
│   └── Dockerfile              # 后端容器化配置
├── web/                        # 前端核心 (Vue 3 + Vite)
│   ├── src/
│   │   ├── main.js             # 【入口】Vue 初始化与插件挂载
│   │   ├── api/                # Axios 请求封装
│   │   ├── assets/             # 静态资源、全局 SCSS 变量
│   │   ├── components/         # 模块化组件
│   │   ├── views/              # 页面视图组件
│   │   ├── store/              # Pinia 状态管理
│   │   └── utils/              # 工具函数 
│   ├── index.html              # SPA 入口模板
│   ├── vite.config.js          # 构建与代理转发配置
│   ├── nginx.conf              # Nginx 反向代理配置 (生产环境)
│   └── Dockerfile              # 前端容器化配置
├── data/                       # 数据持久化目录
│   ├── vector\_db/              # 【存储】ChromaDB 向量索引文件
│   └── metaweave.db            # 【存储】SQLite 关系型数据库文件
├── .env                        # 环境变量
├── .gitignore                  # Git 忽略配置
├── .dockerignore               # Docker 忽略配置
├── docker-compose.yml          # 【编排】一键启动后端、前端、Redis
├── README.md                   # 项目说明文档
├── AGENTS.md                   # Agent代码规范
├── DEVELOPMENT.md              # 项目运行与部署方法
├── ChangeHistory.md            # 变更历史记录
└── TODO.md                     # 开发待办

```  

---

## 开发规范

1. 开发规范写在`开发规范.md`文件中,请务必遵守,以便于团队协作和项目维护.

2. 运行项目的方法写在`DEVELOPMENT.md`文件中.

3. `AGENTS.md`文件详细说明了运用Code Assist Agent开发(如Claude Code,Codex等)时需要注意的点.

4. 项目成员在开发过程中,若有需要修改但是经历不足的地方,则应该写入`TODO.md`;若进行了大幅的修改,则应该在`ChangeHistory.md`文件中记录修改内容和原因,以便于团队成员了解和维护.



