# Phase 1: Mobile App Shell - Discussion Log

> **Audit trail only.** Do not use as input to planning, research, or execution agents.
> Decisions are captured in CONTEXT.md — this log preserves the alternatives considered.

**Date:** 2026-05-26T14:24:10.506Z
**Phase:** 1-Mobile App Shell
**Areas discussed:** 首屏进入方式, 占位活动真实程度, 家长说明出现时机, 记录入口表现

---

## 首屏进入方式

| Question | Options | Selected |
|----------|---------|----------|
| 打开 app 后第一屏更像哪一种？ | 直接开始玩; 先给家长一句说明; 首次打开有轻 onboarding; 其他 | 直接开始玩 |
| 顶部是否显示 app 名称 `小小认知`？ | 显示小标题; 不显示名称; 显示亲子模式提示 | 显示小标题 |
| `开始玩` 点下去后，进入哪种占位活动？ | 固定示例活动; 先选活动类型; 随机一个轻活动 | 固定示例活动 |
| 首屏上的 `看看记录` 怎么处理？ | 显示但弱化; Phase 1 先隐藏; 显示为不可用 | 显示但弱化 |

**User's choice:** Direct-play home with lightweight app name, fixed demo entry, and weak record entry.
**Notes:** User selected recommended options through this area.

---

## 占位活动真实程度

| Question | Options | Selected |
|----------|---------|----------|
| Phase 1 的固定“找苹果”demo 里，图片内容应该怎么处理？ | 真实照片示例; 纯色占位图块; 插画式临时图块 | 真实照片示例 |
| 这个 demo 里除了苹果，还要放几个干扰选项？ | 苹果 + 2 个日常物品; 苹果 + 1 个日常物品; 苹果 + 3 个日常物品 | 苹果 + 2 个日常物品 |
| 这些示例照片从哪里来？ | 仓库内置示例图; 远程占位图 URL; 先用 CSS/渐变模拟照片区域 | 仓库内置示例图 |
| demo 交互反馈要做到什么程度？ | 轻反馈即可; 只证明跳转，不做反馈; 做完整正确/错误状态 | 轻反馈即可 |

**User's choice:** Local real-photo sample demo with apple and two everyday distractor objects.
**Notes:** Feedback should be warm and non-punitive.

---

## 家长说明出现时机

| Question | Options | Selected |
|----------|---------|----------|
| 隐私和健康使用说明应该怎样出现？ | 顶部信息按钮里; 首屏底部一行轻提示; 首次打开弹出一次 | 顶部信息按钮里 |
| 信息按钮打开后，说明内容重点放哪两个？ | 隐私 + 短时使用; 隐私 + 家长陪伴; 短时使用 + 真实世界延伸 | 隐私 + 短时使用 |
| 信息面板的呈现形式？ | 底部 sheet; 居中弹窗; 独立说明页 | 底部 sheet |
| 信息面板里是否要出现“设置”入口？ | 不出现; 放一个不可用的设置占位; 放一个本地清除记录入口 | 不出现 |

**User's choice:** Parent info stays behind a top-bar button and opens as a bottom sheet.
**Notes:** Do not introduce settings in Phase 1.

---

## 记录入口表现

| Question | Options | Selected |
|----------|---------|----------|
| `看看记录` 点开后应该出现什么？ | 空状态 sheet/页面; 轻 toast 提示; 完全不响应 | 空状态 sheet/页面 |
| 空状态是否记录任何真实数据？ | 不记录真实进度，只展示空状态; 记录 demo 点击但标记为本机临时; 完全不进入记录视图 | 不记录真实进度，只展示空状态 |
| 空状态入口形态是什么？ | 底部 sheet 或轻量页面，复用 sheet 模式; 独立全页; toast | 底部 sheet 或轻量页面，复用 sheet 模式 |
| 空状态是否提供下一步动作？ | 提供 `去玩一次` 返回固定 demo; 只显示说明和关闭; 提供不可用的进度预告 | 提供 `去玩一次` 返回固定 demo |

**User's choice:** Empty record state, no real progress data in Phase 1.
**Notes:** User selected option 1 for the first record question, then authorized all subsequent discussion choices to default to recommended options.

---

## the agent's Discretion

- User authorized recommended defaults after the first record-entry decision.
- The agent may choose conservative shell details that avoid premature settings, analytics, accounts, and real progress tracking.

## Deferred Ideas

None.
