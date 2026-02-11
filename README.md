# 🌌 Provelance: 极简 Python 状态引擎

Provelance 是一个将 GitHub Commits 转化为“宇宙时间线”的引擎。它在浏览器中运行 Python 逻辑，实现状态的演化。

## 🚀 核心概念
* **`s` (State)**: 宇宙的**内在状态**。它是持久化的，比如 `s.balance`（余额）或 `s.inventory`（库存）。
* **`p` (Params)**: 宇宙的**外部输入**。它是瞬时的，由你在触发 Action 时通过表单传入，比如 `p.amount`（金额）。

## 🛠️ 快速启动

### 1. 建立物理定律 (RULE)
在“撰写”页面，定义一个名为 `trade` 的规则：
```python
# 使用 p 来修改 s
if p.action == "deposit":
    s.balance += p.amount
    s.last_action = f"存入 {p.amount}"
elif p.action == "withdraw" and s.balance >= p.amount:
    s.balance -= p.amount
    s.last_action = f"取出 {p.amount}"

```

### 2. 触发因果 (ACTION)

切换到“触发”模式，选择 `trade`。

* 引擎会自动解析代码，为你生成 `action` 和 `amount` 的输入框。
* 输入 `deposit` 和 `100`，点击“写入”。
* 观察“观测”界面，你的 `s.balance` 就会增加。
