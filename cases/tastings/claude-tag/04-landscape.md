---
title: 竞争格局与支撑系统
---

## 三维竞争

竞争不在单一维度上，而是三维交叉：

- **模型能力**：谁的模型更可靠、更擅长多步推理
- **上下文密度**：谁能积累更多关于团队的记忆和上下文
- **生态开放性**：谁的工具调用生态更丰富、更标准化

没有一个玩家在三个维度上同时领先。

## 平台-模型张力

Salesforce 拥有 Slack，但无法阻止 Claude Tag 与 Agentforce 竞争——**当模型质量创造足够的拉力时，平台控制力会被侵蚀**。

这是 AI 时代的新动态：平台不再是护城河，模型才是。

## 差异化 vs. 共享能力

- **差异化**：环境感知模式、多人共享记忆——这是 Claude Tag 独有的
- **共享（table-stakes）**：基础 Slack bot 问答——所有玩家都能做，不构成壁垒

## 支撑系统

让一个自主 agent 在企业环境中可部署，需要的不只是核心能力，还有一整套非功能性支撑系统：

- **Agent 身份**：三层权限继承（workspace → channel → thread），独立服务账号
- **Per-channel token 预算**：资源隔离，一个 channel 的重度使用不会影响其他 channel
- **审计日志**：企业合规的必需品——谁让 Claude 做了什么，什么时候做的，结果是什么
- **Ambient mode 管理员控制**：管理员可以逐 channel 开关环境感知，设置触发规则

## 可复用的设计模式

从 Claude Tag 中提炼出的 8 个可复用 pattern：

1. **Thread-as-workspace**：用 thread 作为工作空间，过程公开可追溯
2. **Checklist progress**：异步信任的可视化——用清单展示进度
3. **Agent identity**：独立服务账号，不依附于任何人类用户
4. **Ambient = triggers + judgment + constraints**：环境感知的三层设计
5. **Progressive trust ladder**：从低风险到高风险的渐进式信任
6. **DM-as-sandbox**：私聊作为安全的试探空间
7. **Platform-native interaction**：不造新 UI，用平台原生交互
8. **One-entity-per-scope**：一个作用域一个 agent，不共享
