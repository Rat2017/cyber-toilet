# 赛博厕所 🚽

> let the sacred cyber sewers connect us, and even at our desks, we can take paid dumps.

带薪拉屎模拟器，一个有趣的马桶冲水交互页面。

在线体验：https://rat2017.github.io/cyber-toilet/

## 功能

- 点击马桶冲水（抖动 + 水花粒子动画 + 水面漩涡）
- 四种统计数据：带薪拉屎人数、冲水次数、堵马桶次数、同时在线💩友
- 随机概率堵塞马桶，可用皮搋子疏通（带物理动画）
- 实时在线人数（基于 Firebase Realtime Database）
- 键盘快捷键：空格/回车冲水或疏通
- 响应式设计，支持移动端

## 配置实时在线人数

页面底部的"同时在线💩友"默认显示模拟波动数据。要显示真实在线人数，需配置 Firebase：

1. 前往 [Firebase Console](https://console.firebase.google.com/) 创建一个项目
2. 左侧菜单 → **构建** → **Realtime Database** → **创建数据库**（选择测试模式）
3. 在项目设置 → **常规** → **您的应用** → 添加 Web 应用，获取配置对象
4. 打开 `index.html`，找到 `FIREBASE_CONFIG`，填入 `apiKey`、`databaseURL`、`projectId`
5. 部署后即可显示实时在线人数

### Realtime Database 安全规则

建议将规则设为：

```json
{
  "rules": {
    "presence": {
      ".read": true,
      ".write": true
    }
  }
}
```

## 部署到 GitHub Pages

```bash
git init
git add -A
git commit -m "初始提交"
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

在 GitHub 仓库 Settings → Pages 中，选择 `main` 分支，根目录部署即可。
