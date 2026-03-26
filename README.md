# 🎯 Employee Interview Analyzer

**互联网公司员工访谈结果智能分析 — CodeBuddy Skill**

[![Version](https://img.shields.io/badge/version-2.12.0-blue.svg)](https://github.com/styangqing-cloud/skill-a)
[![License](https://img.shields.io/badge/license-Apache--2.0-green.svg)](LICENSE)
[![CodeBuddy](https://img.shields.io/badge/CodeBuddy-Skill-purple.svg)](https://www.codebuddy.ai)

> 专为互联网公司 HR 设计的**访谈结果智能分析**技能。输入访谈记录/纪要，自动识别访谈场景，智能匹配分析方法论，输出结构化洞察报告。

---

## ✨ 功能亮点

| 特性 | 说明 |
|------|------|
| 🧠 **智能场景识别** | 自动识别 10+ 种访谈场景（入职、离职、绩效、组织诊断等） |
| 📐 **7 大方法论体系** | 杨三角、韦斯伯德六盒、推拉力、冰山模型、BEM、职业锚+GROW、STAR |
| ⚡ **快速分析模式** | v2.12 新增：自动评估复杂度，简单访谈减少 40% 交互 |
| 🔒 **方法论数量控制** | 每次分析严格限制 ≤ 3 种方法论，深度优于广度 |
| 📊 **可视化报告** | 自动生成雷达图、能力矩阵等可视化 HTML 报告 |
| 👤 **多维画像生成** | 支持员工画像、管理干部画像、候选人画像、组织画像 |
| ✍️ **智能文本修正** | 自动修正访谈记录中的错别字和语句不通顺问题 |
| 🤖 **AI 增强维度** | 融入 AI 时代特有的分析视角 |

---

## 🚀 快速安装

### 方式一：一键安装（推荐）

在 CodeBuddy 对话框中输入：

```
/skill install https://github.com/styangqing-cloud/skill-a
```

### 方式二：手动安装

```bash
git clone https://github.com/styangqing-cloud/skill-a.git ~/.codebuddy/skills/employee-interview-analyzer
```

### 验证安装

安装完成后，在 CodeBuddy 中说：

```
帮我分析一下这份访谈记录
```

如果 skill 被正确识别并激活，说明安装成功 ✅

---

## 📋 支持的分析场景

| 场景 | 主方法论 | 辅助方法论 | 输出重点 |
|------|---------|-----------|---------|
| **入职访谈** | 冰山模型 | BEM 模型 | 融入适配 |
| **绩效访谈** | BEM 模型 | 杨三角 | 绩效根因 |
| **离职访谈** | 推拉力理论 | 冰山模型 | 离职原因 |
| **晋升访谈** | 冰山模型 | BEM 模型 | 能力差距 |
| **职业发展** | 职业锚+GROW | 冰山模型 | 发展方向 |
| **团队反馈** | 杨三角 | 冰山模型 | 团队问题 |
| **转岗访谈** | 冰山模型 | 职业锚+GROW | 岗位匹配 |
| **组织诊断** ⭐ | 杨三角 | 冰山模型 | 组织健康 |
| **招聘面试** ⭐ | STAR 面试法 | 冰山模型 | 候选匹配 |
| **综合分析** | 动态匹配 | 最多 2 个辅助 | 趋势洞察 |

---

## 💡 使用示例

### 基本用法

直接在 CodeBuddy 中粘贴访谈记录，然后说：

```
帮我分析一下这份访谈记录
```

Skill 会自动：
1. 识别访谈场景类型
2. 匹配最佳方法论组合
3. 展示分析框架供你确认
4. 生成结构化洞察报告

### 常用提示词

```
# 离职访谈分析
"这是和小张做完离职访谈的纪要，帮我做个分析"

# 组织诊断
"帮我看看这个组织诊断的结果"

# 绩效面谈
"这几份绩效面谈记录，帮我做个综合分析"

# 招聘评估
"分析一下这个候选人的面试表现"

# 指定方法论
"用冰山模型帮我分析这份访谈"

# 多份记录
"这5份访谈记录帮我做个综合趋势分析"
```

### 输入格式

支持多种输入方式：
- 📝 直接粘贴访谈文本
- 📎 上传访谈记录文件（.txt / .md / .docx）
- 🔗 提供腾讯文档链接
- 📋 粘贴结构化的面试评估表

---

## 🧠 7 大方法论体系

<details>
<summary><b>M1 — 杨三角理论</b>（组织能力诊断）</summary>

从**员工思维**、**员工能力**、**员工治理**三个维度进行组织能力诊断。适用于团队反馈分析和组织诊断场景。

</details>

<details>
<summary><b>M2 — 韦斯伯德六盒模型</b>（组织健康评估）</summary>

从**使命**、**结构**、**关系**、**奖励**、**领导**、**支持机制**六个维度评估组织健康状况。

</details>

<details>
<summary><b>M3 — 推拉力理论</b>（离职原因分析）</summary>

分析**推力因素**（驱使离开的原因）和**拉力因素**（吸引离开的原因），深入理解离职动机。

</details>

<details>
<summary><b>M4 — 冰山模型</b>（深层素质挖掘）</summary>

从**知识技能**（水面以上）到**动机价值观**（水面以下）逐层分析，揭示深层素质。

</details>

<details>
<summary><b>M5 — BEM 模型</b>（绩效行为分析）</summary>

基于 Gilbert 的行为工程模型，从**环境因素**和**个人因素**两大维度分析绩效影响。

</details>

<details>
<summary><b>M6 — 职业锚+GROW 模型</b>（职业发展规划）</summary>

结合职业锚定位和 GROW 教练模型，为员工制定个性化发展路径。

</details>

<details>
<summary><b>M7 — STAR 面试法</b>（候选人评估）</summary>

通过**情境(S)**、**任务(T)**、**行动(A)**、**结果(R)**四维分析，系统评估候选人能力。

</details>

---

## 📊 输出报告示例

分析完成后会生成结构化报告，包含：

```
📋 分析报告结构
├── 📌 访谈基本信息（场景、人员、时间等）
├── ✍️ 修正后的访谈文本
├── 📐 方法论分析
│   ├── 主方法论分析结果
│   └── 辅助方法论分析结果
├── 🔍 关键发现（Top 3-5 洞察）
├── 📊 可视化图表（雷达图/矩阵图等）
├── 👤 人员/组织画像
├── 💡 行动建议（按优先级排列）
└── ⚠️ 风险提示
```

---

## 🔗 配套技能

| 技能 | 用途 | 使用阶段 |
|------|------|---------|
| [employee-interview-generator](https://github.com/styangqing-cloud/skill-b) | 访谈提纲生成器 | 访谈**前** |
| **employee-interview-analyzer**（本技能） | 访谈结果分析器 | 访谈**后** |

两个技能共享相同的方法论体系，形成完整的 **访谈前 → 访谈后** 闭环。

---

## 📁 项目结构

```
employee-interview-analyzer/
├── SKILL.md              # 主技能定义文件（核心逻辑）
├── CONSTRAINTS.md        # 方法论约束配置
├── README.md             # 说明文档（本文件）
├── UPGRADE-LOG.md        # 版本升级日志
├── examples/             # 分析示例
│   ├── individual-example.json
│   ├── organization-example.json
│   ├── recruitment-evaluation-example.json
│   └── recruitment-evaluation-output.md
├── references/           # 方法论参考资料
│   ├── yang-triangle-analysis.md
│   ├── weisbord-six-box-analysis.md
│   ├── push-pull-analysis.md
│   ├── iceberg-analysis.md
│   ├── gilbert-bem-analysis.md
│   ├── career-anchor-grow-analysis.md
│   ├── star-analysis.md
│   ├── employee-profile-guide.md
│   ├── manager-profile-guide.md
│   ├── visualization-guide.md
│   └── ...
├── scripts/              # 辅助脚本
│   ├── export_profile.py
│   └── visualization_generator.py
├── src/                  # 核心分析引擎
│   ├── interview_analyzer.py
│   ├── report_generator.py
│   ├── individual/
│   └── organization/
└── templates/            # 报告模板
    └── report-templates.md
```

---

## 📝 版本历史

| 版本 | 日期 | 更新内容 |
|------|------|---------|
| **v2.12.0** | 2026-03 | ⚡ 新增快速分析模式，自动复杂度评估，简单访谈减少 40% 交互 |
| **v2.11.0** | 2026-03 | 👤 管理干部画像对齐 HR 系统 |
| **v2.9.0** | 2026-03 | 🔒 方法论默认优先 2 种（1主+1辅），仅复杂场景扩展至 3 种 |
| **v2.4.0** | 2026-03 | 📊 可视化 HTML 生成与员工画像导出功能 |
| **v2.3.0** | 2026-03 | 🔧 流程优化、方法论限制强化、场景自动识别 |
| **v1.1.0** | 2026-03 | 🆕 新增招聘面试评估模式 |
| **v1.0.0** | 2026-03 | 🎉 初始版本发布 |

---

## ⚙️ 环境要求

- **CodeBuddy** — 需安装 CodeBuddy IDE 插件
- **Python 3.8+** — 可视化报告生成需要（可选）
- **网络访问** — 下载员工头像等功能需要内网访问

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'feat: add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 提交 Pull Request

---

## 📄 许可证

本项目基于 [Apache-2.0](LICENSE) 许可证开源。

---

## 👨‍💻 作者

**tommyyang@tencent**

如有问题或建议，欢迎在 [GitHub Issues](https://github.com/styangqing-cloud/skill-a/issues) 中反馈。
