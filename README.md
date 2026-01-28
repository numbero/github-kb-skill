# Claude GitHub KB Skill

[中文](#中文说明) | [English](#english)

## English

### Overview

A powerful Claude Code skill that transforms Claude into a GitHub Intelligence Officer (GIO). This skill enables Claude to leverage the `gh` CLI tool to search and retrieve real-time information from GitHub, including repositories, issues, pull requests, code snippets, and commit history.

### Features

- 🔍 **Repository Discovery**: Search for repositories with advanced filters (language, stars, activity)
- 🐛 **Bug Investigation**: Find solutions by searching closed issues and pull requests
- 💻 **Code Search**: Locate specific code snippets, configurations, and API implementations
- 📝 **Commit History**: Track code changes and contributions over time
- 🚀 **GitHub API Integration**: Direct access to GitHub REST and GraphQL APIs
- 🤖 **GitHub Copilot CLI**: Integration with GitHub Copilot for AI-powered assistance (v2.86+)

### Prerequisites

- [Claude Code CLI](https://github.com/anthropics/claude-code) installed
- [GitHub CLI (`gh`)](https://cli.github.com/) v2.80.0 or higher (v2.86+ recommended)
- GitHub account authenticated with `gh auth login`

### Installation

1. Clone this repository:
```bash
git clone https://github.com/JayTing511/claude-github-kb-skill.git
```

2. Copy the skill to your Claude skills directory:
```bash
cp -r claude-github-kb-skill ~/.claude/skills/github-kb
```

3. Restart Claude Code or reload skills:
```bash
claude reload
```

### Usage

Invoke the skill when you need to:
- Find open source projects
- Search for code solutions on GitHub
- Debug error messages by finding related issues
- Learn from existing implementations
- Query repositories in your `~/github-kb` directory

#### Example Queries

**Finding repositories:**
```
"Find popular Python machine learning libraries"
"Show me React admin dashboard templates"
```

**Debugging:**
```
"This deployment error: 'ECONNREFUSED' - how to fix?"
"Search for solutions to CloudBot deployment issues"
```

**Learning from code:**
```
"How do others implement JWT authentication in Node.js?"
"Show me examples of Docker compose configurations"
```

### Search Command Reference

| Scenario | Command Example |
|----------|----------------|
| High-star projects | `gh search repos "keyword" --sort stars --limit 10` |
| Recently active projects | `gh search repos "keyword" --sort updated --limit 10` |
| Filter by language | `gh search repos "keyword" --language python` |
| Filter by stars | `gh search repos "keyword" --stars ">1000"` |
| Exclude keywords | `gh search repos -- "react -antd"` |
| Solved bugs | `gh search issues "error" --state closed --label bug` |
| Merged PRs | `gh search prs "feature" --state merged` |
| Code by file type | `gh search code "config" --extension yaml` |
| Commit history | `gh search commits "fix" --repo owner/repo` |

### Configuration

The skill automatically:
- Checks `gh` CLI version on initialization
- Prompts for updates if version is below recommended
- Validates GitHub authentication status

### Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Author

Created by [@JayTing511](https://github.com/JayTing511)

---

## 中文说明

### 项目简介

一个强大的 Claude Code 技能，将 Claude 转变为 GitHub 情报官（GIO）。该技能使 Claude 能够利用 `gh` CLI 工具实时搜索和检索 GitHub 上的信息，包括仓库、issues、PR、代码片段和提交历史。

### 功能特性

- 🔍 **仓库发现**：通过高级过滤器（语言、星标、活跃度）搜索仓库
- 🐛 **Bug 调查**：通过搜索已关闭的 issues 和 PR 找到解决方案
- 💻 **代码搜索**：定位特定的代码片段、配置文件和 API 实现
- 📝 **提交历史**：跟踪代码变更和贡献记录
- 🚀 **GitHub API 集成**：直接访问 GitHub REST 和 GraphQL API
- 🤖 **GitHub Copilot CLI**：集成 GitHub Copilot 实现 AI 辅助（需 v2.86+）

### 前置要求

- 已安装 [Claude Code CLI](https://github.com/anthropics/claude-code)
- [GitHub CLI (`gh`)](https://cli.github.com/) v2.80.0 或更高版本（推荐 v2.86+）
- 通过 `gh auth login` 认证的 GitHub 账户

### 安装步骤

1. 克隆此仓库：
```bash
git clone https://github.com/JayTing511/claude-github-kb-skill.git
```

2. 将技能复制到 Claude 技能目录：
```bash
cp -r claude-github-kb-skill ~/.claude/skills/github-kb
```

3. 重启 Claude Code 或重新加载技能：
```bash
claude reload
```

### 使用方法

在以下场景中调用此技能：
- 查找开源项目
- 在 GitHub 上搜索代码解决方案
- 通过查找相关 issues 调试错误信息
- 学习现有实现
- 查询 `~/github-kb` 目录下的仓库

#### 使用示例

**查找仓库：**
```
"找一些流行的 Python 机器学习库"
"给我看看 React 管理后台模板"
```

**调试问题：**
```
"这个部署错误：'ECONNREFUSED' 怎么解决？"
"搜索 CloudBot 部署问题的解决方案"
```

**学习代码：**
```
"其他人是如何在 Node.js 中实现 JWT 认证的？"
"给我展示一些 Docker compose 配置的例子"
```

### 搜索命令参考

| 场景 | 命令示例 |
|------|---------|
| 找高星项目 | `gh search repos "keyword" --sort stars --limit 10` |
| 找最近活跃项目 | `gh search repos "keyword" --sort updated --limit 10` |
| 按语言筛选 | `gh search repos "keyword" --language python` |
| 按 stars 范围 | `gh search repos "keyword" --stars ">1000"` |
| 排除关键词 | `gh search repos -- "react -antd"` |
| 搜索已解决的 bug | `gh search issues "error" --state closed --label bug` |
| 搜索已合并的 PR | `gh search prs "feature" --state merged` |
| 搜索特定文件类型代码 | `gh search code "config" --extension yaml` |
| 搜索提交记录 | `gh search commits "fix" --repo owner/repo` |

### 配置

技能会自动：
- 在初始化时检查 `gh` CLI 版本
- 如果版本低于推荐版本则提示更新
- 验证 GitHub 认证状态

### 贡献

欢迎贡献！请随时提交 Pull Request。

1. Fork 此仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

### 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

### 作者

由 [@JayTing511](https://github.com/JayTing511) 创建
