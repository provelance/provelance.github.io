# 🌌 Provelance: 极简 Python 状态引擎

Provelance 是一个基于 GitHub Commits 构建的“宇宙时间线”引擎。它将 GitHub 仓库作为数据库，利用 Brython 在浏览器中实现逻辑校验与状态演化。

## 🚀 启动你的宇宙

### 1. 基础设施准备
* **创建一个私有仓库**：在 GitHub 上新建一个 Repo（例如 `my-universe`）。
* **获取 Access Token**：在 GitHub Settings 生成一个具有 `repo` 权限的 Personal Access Token (PAT)。
* **访问地址**：打开你的 Provelance 页面。

### 2. 连接宇宙
* 在顶部输入框填入 `用户名/仓库名` 和你的 `Token`。
* 点击 **“同步”**。如果仓库是空的，你会看到一份内置的启动指引。

### 3. 定义物理定律 (RULE)
* 切换到 **“撰写”** 标签，选择模式为 **“⚖️ 定义”**。
* 输入名称（如 `init_balance`），编写 Python 代码：
    ```python
    s.balance = 100
    s.last_action = "宇宙大爆炸：初始资金"
    ```
* 点击 **“⚡ 写入”**。这会向你的 GitHub 发送第一条“定律”。

### 4. 触发事件 (ACTION)
* 选择模式为 **“🚀 触发”**。
* 选择一个已定义的 Rule，下方会自动根据代码生成输入表单。
* 填写参数并点击 **“⚡ 写入”**，观察 **“观测”** 界面中状态的实时变化。

## 🧠 核心逻辑
* **状态 `s`**：持久化的全局对象。
* **参数 `p`**：由 Action 传入的临时变量。
* **不可逆性**：每一条提交都是宇宙历史的一部分，Provelance 通过回溯整个 Commits 树来重建当前状态。
