<div align="center">

<h1>📖 计算机组成原理 · 系统学习笔记</h1>

<p>
  <strong>Computer Organization and Architecture — Structured Study Notes</strong>
</p>

<p>
  <a href="https://github.com/xiaoluosigithub/Computer-Composition-Principles-Study-Notes/stargazers">
    <img src="https://img.shields.io/github/stars/xiaoluosigithub/Computer-Composition-Principles-Study-Notes?style=flat-square&color=yellow" alt="Stars"/>
  </a>
  <a href="https://github.com/xiaoluosigithub/Computer-Composition-Principles-Study-Notes/network/members">
    <img src="https://img.shields.io/github/forks/xiaoluosigithub/Computer-Composition-Principles-Study-Notes?style=flat-square&color=blue" alt="Forks"/>
  </a>
  <a href="https://github.com/xiaoluosigithub/Computer-Composition-Principles-Study-Notes/commits/main">
    <img src="https://img.shields.io/github/last-commit/xiaoluosigithub/Computer-Composition-Principles-Study-Notes?style=flat-square&color=green" alt="Last Commit"/>
  </a>
  <img src="https://img.shields.io/badge/工具-Obsidian-7C3AED?style=flat-square&logo=obsidian&logoColor=white" alt="Obsidian"/>
  <img src="https://img.shields.io/badge/格式-Markdown-000000?style=flat-square&logo=markdown" alt="Markdown"/>
  <img src="https://img.shields.io/badge/持续更新-进行中-brightgreen?style=flat-square" alt="Status"/>
</p>

<p>
  <b>知识笔记 · 思维导图 · 配套习题</b><br/>
  一份面向考研 / 期末 / 系统学习的计算机组成原理完整笔记仓库
</p>

<br/>

</div>

---

## ✨ 项目亮点

> 本仓库不是简单的课堂截图或教材扫描，而是经过系统整理、结构化组织的**原创学习笔记**，适合期末复习、考研备考以及想要夯实底层硬件知识的同学。

- **三位一体**：每个知识点均配备「知识文档 + 思维导图 + 配套习题」，形成完整的学习闭环
- **Obsidian 原生支持**：使用 `.md` + `.canvas` 格式，在 Obsidian 中可获得最佳阅读与编辑体验，双链笔记随意跳转
- **持续迭代**：笔记随学习进度同步更新，vault 自动备份至 GitHub，始终保持最新状态
- **结构清晰**：按教材章节编号组织，脉络一目了然，方便定点查阅

---

## 📂 仓库结构

```
Computer-Composition-Principles-Study-Notes/
│
├── 计算机组成原理/
│   ├── 知识文件夹/          # 核心知识点笔记（Markdown）
│   │   ├── 3.5高速缓冲存储器/
│   │   ├── 3.6虚拟存储器/
│   │   ├── 4.1指令系统/
│   │   ├── 4.2寻址方式/
│   │   └── 4.3程序的机器级代码表示/
│   │
│   ├── 思维导图/            # Obsidian Canvas 可视化思维导图
│   │   ├── 3.5高速缓冲存储器.canvas
│   │   ├── 3.6虚拟存储器.canvas
│   │   ├── 3.7&3.8 本章小结&常见问题.canvas
│   │   ├── 4.1指令系统.canvas
│   │   ├── 4.2寻址方式.canvas
│   │   └── 4.3程序的机器级代码表示.canvas
│   │
│   └── 习题/               # 各节配套练习题与解析
│       ├── 3.5高速缓冲存储器习题.md
│       ├── 3.6虚拟存储器.md
│       ├── 4.1指令系统.md
│       ├── 4.2寻址方式.md
│       └── 4.3程序的机器级代码表示.md
│
└── README.md
```

---

## 📚 知识覆盖

### 第三章 · 存储系统

| 章节 | 内容概要 |
|------|----------|
| **3.5 高速缓冲存储器 (Cache)​** | Cache 的基本原理、映射方式（直接/全相联/组相联）、替换策略、写策略、性能分析 |
| **3.6 虚拟存储器** | 虚拟地址空间、页表机制、TLB、缺页中断、段页式存储管理 |
| **3.7 & 3.8 本章小结 & 常见问题** | 存储层次结构总结、高频考点梳理、常见易错点 |

### 第四章 · 指令系统

| 章节                 | 内容概要                              |
| ------------------ | --------------------------------- |
| **4.1 指令系统**       | 指令格式、操作码扩展技术、指令类型、RISC vs CISC    |
| **4.2 寻址方式**       | 立即寻址、直接寻址、间接寻址、寄存器寻址、相对寻址、基址/变址寻址 |
| **4.3 程序的机器级代码表示** | 汇编基础、过程调用、栈帧结构、数组与指针的底层表示         |

---

## 🚀 快速开始

### 方式一：在线浏览（推荐）

直接在 GitHub 上点击各 `.md` 文件即可在线预览笔记内容，无需任何配置。

### 方式二：本地 Obsidian（最佳体验）

```bash
# 1. 克隆仓库
git clone https://github.com/xiaoluosigithub/Computer-Composition-Principles-Study-Notes.git

# 2. 打开 Obsidian → 选择「Open folder as vault」
# 3. 选中克隆下来的文件夹根目录即可
```

> **推荐插件**：`Obsidian Canvas`（内置）、`Minimal Theme`、`Dataview`

---

## 🗺️ 学习路线建议

对于初次接触本仓库的同学，推荐按以下顺序学习：

1. **先看思维导图** — 快速建立章节全局认知，理解各知识点之间的关系
2. **精读知识文档** — 深入每一个细节，理解原理而非死记硬背
3. **完成配套习题** — 通过真题/模拟题检验掌握程度，查漏补缺

---

## 🤝 如何贡献

本仓库欢迎一切形式的贡献，无论是纠正笔误、补充遗漏知识点，还是增加新章节内容：

1. Fork 本仓库
2. 新建分支：`git checkout -b feature/your-topic`
3. 提交更改：`git commit -m 'Add: 补充 XXX 章节笔记'`
4. 推送分支并发起 Pull Request

---

## ⭐ Star History

如果这份笔记对你有帮助，请点一个 **Star** 支持一下，这是对作者最大的鼓励！

---

## 📄 许可证

本项目采用 [MIT License](LICENSE) 开源协议，欢迎学习与二次分享，转载请注明出处。

---

<div align="center">
  <sub>Made with ❤️ by <a href="https://github.com/xiaoluosigithub">xiaoluosi</a> · 持续更新中</sub>
</div>
