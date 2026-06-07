# Frontend Delivery Reviewer / 前端交付评审器

Frontend Delivery Reviewer is a Codex skill for higher-quality frontend delivery. It adds two gates to frontend work:

`Solution Research Gate -> Implementation -> Frontend Expert Review Gate`

`Frontend Delivery Reviewer` 是一个用于提升前端交付质量的 Codex Skill。它在前端开发流程中加入两个门禁：

`方案调研与选择 -> 实现开发 -> 前端专家评审`

## Why / 为什么需要它

Frontend features can easily become a pile of cards, buttons, and partial interactions. This skill helps an agent decide how a feature should fit into the product before coding, then score the result before delivery.

前端功能很容易变成卡片、按钮和局部交互的堆砌。这个 skill 的目标是：在写代码前先判断功能应该如何进入产品结构，交付前再用专家评审标准打分，避免“能跑但不好用、不美观、不成体系”。

## Workflow / 工作流

```text
Requirement
-> Solution Research Gate
-> Implementation
-> Deterministic Checks
-> Browser Evidence
-> Frontend Expert Review
-> Fix Until Pass
-> Delivery
```

```text
用户需求
-> 方案调研与选择
-> 实现开发
-> 确定性检查
-> 浏览器证据
-> 前端专家评审
-> 不达标返工
-> 达标交付
```

## What It Checks / 检查什么

- Requirement fit / 是否真正满足用户需求
- UX flow / 交互流程是否顺畅
- Visual design / 视觉层级、间距、排版、颜色是否专业
- Responsive layout / 桌面、平板、手机是否正常
- Accessibility / 对比度、焦点、语义和可访问性
- Code quality / 是否符合项目结构和本地模式
- Stability / 是否有 console error、接口错误或明显不稳定

## Pass Criteria / 通过标准

- Overall score >= 85 / 总分不低于 85
- No blockers / 没有阻断问题
- Core categories meet minimum thresholds / 核心维度达到最低分
- Browser evidence exists when feasible / 可行时必须有浏览器渲染证据
- Failed reviews must be fixed and reviewed again / 未达标必须返工后重新评审

## Files / 文件结构

```text
frontend-delivery-reviewer/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── solution-research-template.md
    ├── frontend-review-rubric.md
    └── frontend-review-template.md
```

## Intended Use / 适用场景

Use this skill for:

- new frontend pages / 新前端页面
- dashboards or workbenches / 仪表盘或工作台
- complex UI interactions / 复杂交互
- redesigns / 页面改版
- product UI quality gates / 产品前端质量门禁

Small copy changes, tiny bug fixes, or purely backend work can skip the full workflow.

小文案修改、小 bug 修复、纯后端任务可以跳过完整流程。
