# 大渡河 1935 · 飞夺泸定桥

> 一个可以在浏览器里走进去的红色历史场景——全部由 AI（Kimi K3 Pro）对话式搭建，three.js 程序化建模，零依赖、离线可玩。

**在线体验：https://fzhbcbdttsufs.ok.kimi.link**

![十三根铁索](screenshots/shot6_onbridge_firstperson.jpg)

## 这是什么

以 1935 年红军飞夺泸定桥为背景的网页 3D 第一人称场景：

- 104 米悬垂铁索桥，9 根底链 + 4 根扶手链，全部由椭圆铁环交替咬合而成；
- 桥板三态可切换：无桥板（历史原貌）／铺满／残缺燃烧；
- 大渡河急流、V 形尾流、岩壁、栈道、两岸桥头亭与县城框架；
- 昼夜天气系统：晴日、黄昏、晴夜、雨天自动循环；
- 对岸川军阵地：Tripo AI 生成的士兵／军官／机枪模型，会上桥开火、迫击炮砸起水花（当前为体验版，玩家无伤）；
- 全程约 175 draw calls / 58 万三角形，战斗热循环零分配。

## 运行

- 直接双击 `index.html`（建议 Chrome / Edge），或
- `python -m http.server 8124` 后访问 http://localhost:8124

## 目录

```
index.html        入口（版本号在 var v='63'）
three.min.js      three.js r147（本地化，无外网依赖）
js/               bridge.js（桥体）· world.js（河谷+战斗）· main.js（主循环/玩家/状态机）
assets/           AI 生成模型（GLB 源文件 + 转换后的 js 几何）与树几何
tools/glb2js.py   GLB→js 离线转换器（含士兵/军官/机枪调色板，sRGB→linear）
skill/            web3d-scene-experience：本项目沉淀的可复用方法论 skill
screenshots/      实景截图
```

## 文档

- [DEV-EXPERIENCE.md](DEV-EXPERIENCE.md) —— 开发经验沉淀：提示词方法论、3D 构建手法、性能编年史、踩坑 Top12
- [HANDOFF.md](HANDOFF.md) —— 交接文档：系统细节、关键数值、完整踩坑清单、测试验收手册
- [DESIGN.md](DESIGN.md) —— 设计文档：史实边界与三关战役规划

## 开源与共建

代码与 skill 以 MIT 协议开源。欢迎一起搭建更多长征场景——雪山、草地、赤水……目标是把它们串成一条"数字长征路"。

Issue 和 PR 随时开。如果你想用这套方法做自己的场景，先看 `skill/` 和 [DEV-EXPERIENCE.md](DEV-EXPERIENCE.md)。

## 致谢

- 场景由 Kimi K3 Pro 对话式搭建；
- 士兵/军官/机枪模型由 Tripo AI 生成；
- 向 22 名飞夺泸定桥的红军勇士致敬。

---

*红军不怕远征难，万水千山只等闲。*
