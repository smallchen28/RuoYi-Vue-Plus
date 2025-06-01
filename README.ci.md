# RuoYi-Vue-Plus 自动化CI说明

本项目已集成 GitHub Actions 自动化CI流程，支持后端（Maven）与前端（Vue）自动构建与测试。

## 目录结构
- `RuoYi-Vue-Plus/`：后端Spring Boot主工程，使用Maven管理
- `plus-ui/`：前端Vue 3项目，使用Vite和npm管理

## 自动化流程（.github/workflows/ci.yml）
- 触发条件：main、master、dev分支的push和pull request
- 后端：
  - 使用JDK 21
  - Maven编译并运行所有单元测试
- 前端：
  - Node.js 18
  - 安装依赖并构建生产包
  - （如有前端测试脚本可解开注释自动测试）

## 本地开发
### 后端
```bash
cd RuoYi-Vue-Plus
mvn clean test # 运行所有单元测试
```

### 前端
```bash
cd plus-ui
npm install --registry=https://registry.npmmirror.com
npm run dev # 启动开发环境
npm run build:prod # 构建生产包
```

## 贡献与提交
1. 提交代码前请确保本地测试通过。
2. 推送到GitHub后，CI会自动执行构建与测试。

---
如需更多帮助，请查阅各子项目README或联系维护者。
