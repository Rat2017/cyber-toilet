# 赛博厕所 🚽

> let the sacred cyber sewers connect us, and even at our desks, we can take paid dumps.

带薪拉屎模拟器 — 所有用户共享同一个马桶，实时同步数据。

在线体验：https://rat2017.github.io/cyber-toilet/

## 功能

- **实时共享数据** — 所有用户的冲水、堵塞数据实时同步（基于 Firebase）
- 点击马桶冲水 — 抖动动画 + 水花粒子 + 水面漩涡
- 随机概率堵塞马桶，可用皮搋子疏通
- 多语言支持（中/EN），自动识别浏览器语言
- 键盘快捷键：空格/回车冲水或疏通
- 响应式设计，支持移动端

## 配置 Firebase（共享数据必需）

页面默认使用本地存储（单人模式）。要开启跨用户实时同步：

1. 前往 [Firebase Console](https://console.firebase.google.com/) 创建项目
2. 左侧菜单 → **构建** → **Realtime Database** → **创建数据库**
3. 选择**测试模式**（开发阶段）或设置以下安全规则：

```json
{
  "rules": {
    "stats": {
      ".read": true,
      ".write": true
    }
  }
}
```

4. 在项目设置 → **常规** → **您的应用** → 添加 **Web 应用**
5. 复制 `firebaseConfig` 中的 `apiKey`、`databaseURL`、`projectId`
6. 打开 `index.html`，找到 `FIREBASE_CONFIG` 填入这三项
7. 部署后所有用户共享同一份数据

## 本地部署

```bash
git clone https://github.com/Rat2017/cyber-toilet.git
cd cyber-toilet
# 直接用浏览器打开 index.html 即可
```
