# employee-interview-analyzer

员工访谈分析技能 - 支持**个体分析**和**组织分析**两种模式。

> **版本：** v1.0.0  |  **生产者：** tommyyang@tencent  |  **创建日期：** 2026-03-13

## 快速开始

```bash
# 个体分析
python -m src.interview_analyzer \
  --input examples/individual-example.json \
  --output output/individual-report.md

# 组织分析
python -m src.interview_analyzer \
  --input examples/organization-example.json \
  --output output/organization-report.md
```

## 两种分析模式

### 模式 A：个体访谈分析

对单个员工的访谈内容进行深度分析：

**输入：**
```json
{
  "analysis_mode": "individual",
  "employee": {
    "profile": {...},
    "interview": {...},
    "transcript": "完整访谈文本..."
  }
}
```

**输出：**
- ✅ 假设验证结果（基于画像的预设假设）
- ✅ 矛盾信号检测（画像标签 vs 访谈内容）
- ✅ 新增洞察提取
- ✅ 风险信号识别
- ✅ 个人画像更新建议
- ✅ 个人行动建议

### 模式 B：组织诊断分析

对多个员工的访谈内容进行聚合分析：

**输入：**
```json
{
  "analysis_mode": "organization",
  "organization": "XX 事业部",
  "strategic_goal": "组织战略目标",
  "employees": [...]
}
```

**输出：**
- ✅ 杨三角三维度健康度
- ✅ 跨个体模式识别（≥70% 提及 = 系统问题）
- ✅ 群体差异分析
- ✅ 战略对齐度评估
- ✅ 最短木板识别
- ✅ 优先级干预建议

## Python API

```python
from src import InterviewAnalyzer, EmployeeData

analyzer = InterviewAnalyzer()

# 个体分析
individual_result = analyzer.analyze({
    "analysis_mode": "individual",
    "employee": {...}
})

# 组织分析
org_result = analyzer.analyze({
    "analysis_mode": "organization",
    "employees": [...],
    "strategic_goal": "..."
})

# 生成报告
report = analyzer.generate_report(result, output_path="output/report.md")
```

## 输出示例

### 个体报告结构

```markdown
# 访谈洞察报告 - 张三

## 📊 假设验证结果
| 假设 | 验证状态 | 置信度 |
|------|----------|--------|
| 高潜员工可能遇到成长瓶颈 | ✅ 确认 | 高 |

## ⚠️ 矛盾信号检测
| 画像标签 | 访谈信号 | 矛盾程度 |
|----------|----------|----------|
| 高投入 | 多次提及"倦怠" | 🔴 高 |

## 🆕 新增洞察
1. **跨部门影响力不足** 🆕
   - 证据：3 次提及"推不动其他部门"
   - 根因：缺乏跨部门 SLA 机制

## 🚨 风险信号
- 🔴 **retention_risk**: 检测到 3 条离职风险信号

## 🏷️ 画像更新建议
- 新增标签：跨部门协作挑战，burnout 预警
- 风险等级：medium

## 📋 行动建议
1. 🔴 HRBP 保留面谈（1 周内）
2. 🟡 工作负荷评估（2 周内）
```

### 组织报告结构

```markdown
# 组织诊断报告 - XX 事业部

## 📊 杨三角健康度总览
        员工思维 (愿不愿意)
              6.2/10 🟡
             /       \
   员工能力 (能不能) ——— 员工治理 (允不允许)
        7.5/10 🟢           5.4/10 🔴

**综合得分：6.4/10** 🟡 需干预
**最短木板：员工治理**

## 🚨 优先级干预建议
### 🔴 第一优先级（立即行动）
1. 跨部门 SLA 机制
2. 绩效评估校准机制
```

## 文件结构

```
employee-interview-analyzer/
├── SKILL.md
├── README.md
├── src/
│   ├── interview_analyzer.py    # 主分析器
│   ├── report_generator.py       # 报告生成器
│   ├── individual/
│   │   └── individual_analyzer.py  # 个体分析器
│   └── organization/
│       └── org_analyzer.py         # 组织分析器
├── examples/
│   ├── individual-example.json
│   └── organization-example.json
└── output/
```

## 相关技能

- `employee-interview-generator` - 生成访谈提纲
- `org-diagnosis-yang-triangle` - 杨三角组织诊断（本技能复用）

## 版本

- v1.0.0 - MVP 版本，支持个体分析和组织分析

## 许可证

MIT
