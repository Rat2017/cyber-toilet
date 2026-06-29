# 赛博厕所 🚽

> let the sacred cyber sewers connect us, and even at our desks, we can take paid dumps.

带薪拉屎模拟器 — 所有用户共享同一个马桶，数据实时云端同步。

在线体验：https://rat2017.github.io/cyber-toilet/

## 功能

- 所有用户的冲水、堵塞数据通过 Gist API 云端共享
- 进入页面自动同步最新数据，也可点击右上角「🔄 同步」手动刷新
- 点击马桶冲水 — 抖动动画 + 水花粒子 + 水面漩涡
- 随机概率堵塞马桶，可用皮搋子疏通
- 多语言支持（中/EN），自动识别浏览器语言
- 键盘快捷键：空格/回车冲水或疏通
- 响应式设计，支持移动端

## 技术实现

数据存储在 GitHub Gist 中，通过 Gist API 实现读写：
- **读取**：页面加载时 + 点击「🔄 同步」按钮
- **写入**：每次冲水/堵塞/疏通时自动同步
- **同步按钮**：右上角随时点击刷新最新数据

## 本地部署

```bash
git clone https://github.com/Rat2017/cyber-toilet.git
cd cyber-toilet
# 直接用浏览器打开 index.html 即可
```
