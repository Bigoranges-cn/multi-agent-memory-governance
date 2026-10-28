# Multi-Agent Memory Governance

[English](#english) | [简体中文](#简体中文)

## English

A privacy-first Skill for designing and operating a private, review-gated memory repository across AI assistants, devices, and terminal instances.

It helps users keep durable rules and verified project facts synchronized without copying raw conversations, sharing credentials, or allowing one terminal to overwrite another terminal's local state.

## What it provides

- Three-part identities: `assistant__device__instance`
- Separate global, assistant-family, terminal-instance, project, and proposal scopes
- Owner approval before durable writes
- Target version checks and conflict stopping
- Event-triggered synchronization instead of per-message synchronization
- Sanitized repository templates and a publication safety checklist

## Package layout

```text
plugin.json
skills/
  multi-agent-memory-governance/
    SKILL.md
    agents/openai.yaml
    references/
    assets/repository-template/
```

The first release is instruction-only and uses tools already available to the host. It does not require an MCP server, API key, or hosted service.

## Install

### Codex marketplace source

```shell
codex plugin marketplace add Bigoranges-cn/multi-agent-memory-governance
```

Restart the ChatGPT desktop app, open the Plugins Directory, select the `Bigoranges-cn Skills` source, and install `Multi-Agent Memory Governance`.

### Manual Skill installation

Clone this repository, then copy `skills/multi-agent-memory-governance` into your Codex Skills directory. Review the Skill and its supporting files before enabling it.

## Example prompts

```text
Use $multi-agent-memory-governance to design a private memory repository for three AI assistants on two devices.

Use $multi-agent-memory-governance to audit my existing AI memory repository without modifying it.

Use $multi-agent-memory-governance to onboard one new terminal and show the complete proposal before writing.
```

## Privacy model

Use this public repository only for the reusable method and templates. Store real identities, device paths, project facts, and memory in a separate private repository controlled by the user.

Never copy a private memory repository into a public fork.

## Development status

Version `0.1.0` is a local release candidate. Review and test it before publishing or adding it to a marketplace.

Behavioral test cases are listed in [tests/behavior-cases.md](tests/behavior-cases.md).

## License

MIT. See [LICENSE](LICENSE).

## 简体中文

这是一个隐私优先的 Skill，用于在多个 AI、设备和终端实例之间建立私有、经人工审核后才生效的长期记忆仓库。

它解决的重点不是“保存所有对话”，而是安全地保存已确认的长期规则、项目事实、终端能力和跨设备交接信息。

### 主要能力

- 使用 `assistant__device__instance` 区分每个写入者
- 隔离全局规则、AI 专属规则、终端本地信息、项目事实和待审核提案
- 所有持久写入均需 owner 明确批准
- 写入前重新检查目标版本，发现并发变化立即停止
- 按重要会话和重要事件同步，不逐条消息同步
- 提供脱敏仓库模板和公开发布安全检查清单

### 安装

在 Codex CLI 中添加 GitHub marketplace 来源：

```shell
codex plugin marketplace add Bigoranges-cn/multi-agent-memory-governance
```

重启 ChatGPT 桌面应用，在 Plugins Directory 中选择 `Bigoranges-cn Skills` 来源，然后安装 `Multi-Agent Memory Governance`。

也可以克隆本仓库，把 `skills/multi-agent-memory-governance` 复制到本机 Codex Skills 目录。启用前应先审核 Skill 及其引用文件。

### 使用示例

```text
使用 $multi-agent-memory-governance，为三种 AI 和两台电脑设计一个私有记忆仓库。

使用 $multi-agent-memory-governance，只读审核我现有的 AI 记忆仓库，不做修改。

使用 $multi-agent-memory-governance，接入一个新终端，并在写入前展示完整提案。
```

### 隐私原则

公开仓库只保存通用方法、模板和虚构示例。真实用户名、设备路径、项目事实和长期记忆必须保存在用户自己控制的私有仓库中。

绝不能把真实私有记忆仓库直接复制或派生为公开仓库。


