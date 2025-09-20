# Unlearning Attack Survey 🛑🔓

> A comprehensive survey on **attacks against machine unlearning systems** — exploring vulnerabilities in data deletion mechanisms through systematic categorization of attack types, scenarios, and threat models.

📖 **目标**：本仓库旨在系统梳理和分类针对机器学习中“数据遗忘”（Machine Unlearning）机制的各类**攻击方法**（Unlearning Attacks），揭示当前遗忘技术的安全与隐私风险，为构建可信赖、可审计的模型遗忘能力提供参考。

🔧 适用于：隐私计算、联邦学习、GDPR/CCPA 合规研究、模型安全、可信AI等领域研究者与实践者。

---

## 📚 目录

- [1. 背景介绍](#-背景介绍)
- [2. 攻击分类体系](#-攻击分类体系)
- [3. 贡献指南](#-贡献指南)

---

## 🌐 背景介绍

随着 GDPR、CCPA 等数据隐私法规的实施，“被遗忘权”（Right to be Forgotten）推动了 **机器学习中的数据遗忘**（Machine Unlearning）技术的发展。理想情况下，模型应在不重新训练的前提下，**完全移除特定数据的影响**。

然而，越来越多的研究表明，许多遗忘机制存在漏洞，攻击者可通过各种手段：
- 推断某数据是否曾被训练或“遗忘”
- 恢复被遗忘数据的信息
- 绕过遗忘过程，保留数据影响

这类攻击统称为 **Unlearning Attacks**，它们挑战了“遗忘”的可信性与安全性。

本仓库聚焦于梳理这些攻击方法，按 **攻击类型、场景与威胁模型** 进行分类，帮助研究者理解当前风险边界。

---

## 🔍 攻击分类体系

我们从三个维度对 unlearning attacks 进行系统分类：

### 1. 攻击类型（Attack Type）
| 类型 | 描述 |
|------|------|
| **成员推断攻击 (MIA)** | 判断某样本是否在训练集或未被完全遗忘 |
| **数据中毒攻击 (Data Poison)** | 通过查询重建模型，对比前后差异 |
| **反转攻击 (Inversion Attack)** | 分析遗忘前后模型行为差异，反推数据 |
| **遗忘绕过 (Unlearning Circumvention)** | 恶意保留数据影响，欺骗“已遗忘”状态 |
| **后门遗忘攻击** | 在遗忘过程中植入后门，实现隐性记忆 |

### 2. 攻击场景（Attack Scenario）
- 单样本遗忘（Single-point Unlearning）
- 批量遗忘（Batch Unlearning）
- 联邦遗忘（Federated Unlearning）
- 在线/增量遗忘（Online Unlearning）
- 多请求连续遗忘（Sequential Unlearning）

### 3. 威胁模型（Threat Model）
- **黑盒**（Black-box）：仅访问模型 API 输出
- **白盒**（White-box）：可获取模型参数、梯度
- **灰盒**（Gray-box）：了解训练流程或架构
- **数据持有者攻击**：控制部分训练/遗忘请求

---

## 💡 贡献指南

欢迎贡献！你可以：

1. **添加新论文**：在 [论文表](#-论文总览表) 中添加一行，或提交 PR。
2. **完善分类**：对现有论文补充缺失字段。
3. **撰写分析**：为某篇论文写详细解读（可放在 `/papers/` 目录下）。
4. **提出新分类**：如有新攻击类型或场景，欢迎 issue 讨论。

📌 **贡献步骤**：
```bash
fork 本仓库
git clone https://github.com/your-username/unlearning-attack-survey.git
# 编辑 README 或添加文件
git add .
git commit -m "Add new paper: [Title]"
git push
# 提交 Pull Request
