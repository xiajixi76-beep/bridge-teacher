# 省少赛教师管理系统 - 项目备忘

## 项目信息
- **名称**: 2026年浙江省少年桥牌团体赛 - 教师管理系统
- **本地路径**: `C:/Users/Administrator/WorkBuddy/Claw/`
- **核心文件**: `index.html`（单页应用，含嵌入式数据）+ `header.png`（头图）
- **数据文件**: `students_data.json`
- **GitHub**: `xiajixi76-beep/bridge-teacher`
- **Render 部署配置**: `render.yaml`（Static Site，自动从 GitHub 拉取）
- **线上地址（多平台）**:
  - Render（推荐，国内可访问）: https://bridge-teacher.onrender.com/
  - 自有服务器: http://175.178.67.35/bridge/
  - GitHub Pages（备用）: https://xiajixi76-beep.github.io/bridge-teacher/
- **推送方式**: git push（token 已配在 remote URL 中）
- **自有服务器**: 175.178.67.35，root + c.pem，部署到 /root/zhibaotong/frontend/bridge/
- **更新流程**: 改 index.html → git push → Render 自动部署 → 手动更新服务器（SFTP）

## 待办事项
- [ ] **房间号更新**：后续拿到房间号分配后，需要更新到网站中（可能需要新字段 `room_number`，并在学生卡片中展示）

## 数据源
- `省少赛住宿与出行方式(3).xlsx` — 主数据（296人）
- `26省少赛住宿安排(4).xlsx` — 住宿分房安排
- `省少赛组队(5).xlsx` — 缴费、队伍、教练
- `2026桥牌省少赛温馨提示(4)(1).pdf` — 赛前须知
- `2026桥牌省少赛赛程表(1).pdf` — 原始赛程
- `日程表.pdf` — 最新赛程（桌面）

## 已修复的关键 Bug
- `renderGroupFilters()` 中嵌套单引号导致整站 JS 崩溃 → 改用 `data-*` + `addEventListener`
