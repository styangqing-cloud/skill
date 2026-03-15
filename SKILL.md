---
name: employee-interview-analyzer
description: 员工访谈分析技能 - 基于访谈内容进行深度分析，支持个体分析、组织分析和招聘面试评估三种模式
author: tommyyang@tencent
github: https://github.com/styangqing-cloud
license: MIT
last_updated: 2026-03-15
version: 1.1.0
---

# employee-interview-analyzer

员工访谈分析技能 - 基于访谈内容进行深度分析，支持**个体分析**和**组织分析**两种模式。

## 元信息

| 项目 | 信息 |
|------|------|
| **技能名称** | employee-interview-analyzer |
| **版本号** | v1.0.0 |
| **生产者** | tommyyang@tencent |
| **创建日期** | 2026-03-13 |
| **最后更新** | 2026-03-13 |
| **许可证** | Apache-2.0 |
| **主页** | https://github.com/openclaw/workspace |
| **仓库** | https://github.com/openclaw/workspace/tree/main/skills/employee-interview-analyzer |

## 描述

本技能基于访谈原文进行深度分析，支持**三种分析模式**：

### 模式 A：个体访谈分析（Employee Insight Loop）
对单个员工的访谈内容进行分析，输出：
- 假设验证结果（基于员工画像的预设假设）
- 矛盾信号检测（画像标签 vs 访谈内容）
- 新增洞察提取
- 个人画像更新建议
- 个人行动建议

### 模式 B：组织诊断分析（Org Diagnosis）
对多个员工的访谈内容进行聚合分析，输出：
- 杨三角三维度健康度（员工思维 × 员工能力 × 员工治理）
- 跨个体模式识别（≥70% 提及 = 系统问题）
- 群体差异分析（管理者 vs 员工/不同绩效/不同 tenure）
- 矛盾信号检测（认知差异）
- 战略对齐度评估
- 最短木板识别
- 组织干预建议

### 模式 C：招聘面试评估（Candidate Evaluation）⭐ 新增
对招聘面试的文本记录进行分析，结合候选人画像和岗位要求，输出：
- 候选人画像分析（基于简历）
- 岗位匹配度评估（基于 JD 和胜任力模型）
- 面试表现评估（基于面试文本）
- 综合评分（能力/经验/文化/潜力）
- 录用建议（强烈推荐/推荐/待定/不推荐）
- 候选人画像更新（补充面试评估结果）

## 核心功能

### 个体分析功能
- ✅ 基于画像生成分析假设
- ✅ 假设验证（确认/推翻/不确定）
- ✅ 矛盾信号检测（画像标签 vs 访谈内容）
- ✅ 情绪/风险信号识别
- ✅ 主题聚类（HR 维度）
- ✅ 根因分析（5 Why 框架）
- ✅ 个人画像更新建议

### 招聘面试评估功能 ⭐ 新增
- ✅ 候选人画像分析（简历解析）
- ✅ 岗位匹配度评估（JD + 胜任力模型）
- ✅ 面试表现评估（STAR 回答质量）
- ✅ 综合评分（100 分制）
- ✅ 录用建议生成
- ✅ 候选人画像更新（面试评估补充）

### 组织分析功能
- ✅ 杨三角三维度分析（15 个子维度）
- ✅ 跨个体模式识别
- ✅ 群体差异分析
- ✅ 矛盾信号检测（管理者 vs 员工认知差异）
- ✅ 战略对齐度评估
- ✅ 最短木板识别
- ✅ 优先级干预建议生成

## 输入

### 个体分析模式

```json
{
  "analysis_mode": "individual",
  "employee": {
    "profile": {
      "name": "张三",
      "level": "L2-1",
      "performance": "G",
      "tenure_months": 18,
      "is_manager": true,
      "team": "产品组",
      "tags": ["高潜", "项目驱动型"]
    },
    "interview": {
      "type": "定期 1v1",
      "date": "2026-03-10",
      "interviewer": "李四 (HRBP)",
      "framework_used": "employee-interview-generator v2.4"
    },
    "transcript": "完整访谈文本..."
  }
}
```

### 招聘面试评估模式 ⭐ 新增

```json
{
  "analysis_mode": "recruitment",
  "candidate": {
    "profile": {
      "name": "孙骁",
      "work_years": 14,
      "current_company": "钉钉",
      "current_position": "高级产品专家",
      "education": "待确认",
      "skills": ["AI 产品设计", "团队管理", "企业级产品"],
      "experience": [
        {
          "company": "钉钉",
          "position": "基础 AI 产品负责人",
          "duration": "2020.3 - 至今",
          "achievements": ["AI 助理 DAU 40 万", "连续三年闪电侠奖"]
        }
      ]
    },
    "job": {
      "title": "AI 产品策划负责人",
      "level": "P7/P8",
      "department": "腾讯文档",
      "responsibilities": ["AI 产品规划", "团队管理", "技术协同"],
      "requirements": ["懂 AI", "懂产品设计", "团队管理经验"],
      "competency_model": {
        "ai_product": "AI 产品设计和落地能力",
        "leadership": "团队管理和人才培养",
        "collaboration": "跨部门技术协同"
      }
    },
    "interview": {
      "type": "HR 面",
      "date": "2026-03-13",
      "interviewers": ["HR", "业务负责人"],
      "duration_minutes": 60,
      "transcript": "完整面试文本记录..."
    }
  }
}
```

**输出：**
```markdown
# 候选人面试评估报告 - 孙骁

## 📊 候选人画像分析
## 🎯 岗位匹配度评估
## 💬 面试表现评估
## 📈 综合评分（100 分制）
## ✅ 录用建议
## 🔄 候选人画像更新
```

### 组织分析模式

```json
{
  "analysis_mode": "organization",
  "organization": "XX 事业部",
  "diagnosis_period": "2026-Q1",
  "strategic_goal": "打造行业领先的 AI 产品能力",
  "employees": [
    {
      "profile": {...},
      "interview": {...},
      "transcript": "..."
    }
  ]
}
```

## 输出

### 个体分析报告

```markdown
# 访谈洞察报告 - 张三 2026-03-10

## 📊 假设验证结果
| 假设 | 验证状态 | 关键证据 | 置信度 |
|------|----------|----------|--------|
| 高潜员工可能遇到成长瓶颈 | ✅ 确认 | "感觉最近半年学不到新东西了" | 高 |

## ⚠️ 矛盾信号检测
| 画像标签 | 访谈信号 | 矛盾程度 | 可能解释 |
|----------|----------|----------|----------|
| 高投入 | 多次提及"倦怠""想休息" | 高 | burnout 风险 |

## 🆕 新增洞察
1. **跨部门影响力不足**（新标签候选）
   - 证据：3 次提及"推不动其他部门"
   - 建议：安排导师/提供跨部门项目机会

## 🏷️ 画像更新建议
- add_tags: ["跨部门协作挑战", "burnout 预警"]
- risk_level: medium
- follow_up: HRBP 介入（2 周内）
```

### 组织分析报告

```markdown
# 组织诊断报告 - XX 事业部 2026-Q1

## 📊 杨三角健康度总览
        员工思维 (愿不愿意)
              6.2/10 🟡
             /       \
   员工能力 (能不能) ——— 员工治理 (允不允许)
        7.5/10 🟢           5.4/10 🔴

**综合得分：6.4/10** 🟡 需干预
**最短木板：员工治理**

## 🚨 优先级干预建议
### 🔴 第一优先级（1 个月内）
1. 跨部门 SLA 机制
2. 绩效评估校准机制
```

## 使用方法

### CLI 方式

```bash
# 个体分析
openclaw run employee-interview-analyzer \
  --mode individual \
  --input employee-zhangsan.json \
  --output output/zhangsan-report.md

# 组织分析
openclaw run employee-interview-analyzer \
  --mode organization \
  --input org-input.json \
  --output output/org-diagnosis.md
```

### Python API

```python
from employee_interview_analyzer import InterviewAnalyzer

analyzer = InterviewAnalyzer()

# 个体分析
individual_result = analyzer.analyze_individual(
    employee_data=emp_data,
    generate_hypotheses=True
)

# 组织分析
org_result = analyzer.analyze_organization(
    employees=employees,
    strategic_goal="打造行业领先的 AI 产品能力",
    framework="yang_triangle"
)

# 生成报告
report = analyzer.generate_report(result, format="markdown")
```

## 分析框架

### 个体分析框架

| 分析维度 | 方法论 | 输出 |
|----------|--------|------|
| 假设验证 | 假设驱动分析 | 确认/推翻/不确定 |
| 矛盾检测 | 语义对比 | 矛盾信号列表 |
| 主题聚类 | HR 维度编码 | 高频主题 |
| 根因分析 | 5 Why 框架 | 根因链条 |
| 风险评估 | 信号强度检测 | 风险等级 |

### 组织分析框架（杨三角）

```
        员工思维 (愿不愿意)
        - 工作动机
        - 敬业度
        - 文化认同
        - 归属感
        - 离职风险
       /               \
      /                 \
     /                   \
员工能力 (能不能) ————— 员工治理 (允不允许)
- 专业技能              - 组织架构
- 核心胜任力            - 流程机制
- 学习敏锐度            - 信息系统
- 管理能力              - 激励机制
- 人才密度              - 决策效率
```

## 配置示例

```yaml
# analysis-config.yaml
skill: "employee-interview-analyzer"

# 个体分析配置
individual:
  generate_hypotheses: true
  hypothesis_sources:
    - profile_tags
    - performance_level
    - tenure_range
  contradiction_detection: true
  root_cause_analysis: true

# 组织分析配置
organization:
  framework: "yang_triangle"
  pattern_threshold: 0.7  # ≥70% 提及 = 系统问题
  segment_analysis: true
  contradiction_detection: true
  strategy_alignment: true

# 输出配置
output:
  formats:
    - type: "markdown"
      path: "/output/"
  generate_executive_summary: true
  generate_individual_reports: true
```

## 相关技能

- `employee-interview-generator` - 生成访谈提纲
- `tencent-docs` - 腾讯文档输入输出
- `feishu_bitable_*` - 飞书文档输入输出

## 版本

- v1.1.0 - 新增招聘面试评估模式（候选人画像 + 岗位匹配 + 面试评估）
- v1.0.0 - MVP 版本，支持个体分析和组织分析（杨三角框架）

## 许可证

MIT