# Betaflight Assistant

> **项目仍处于开发阶段，尚未完成。暂不建议普通用户下载、安装或用于实际飞行。**

Betaflight Assistant 是一个围绕 Betaflight Configurator 进行开发的实验性项目，尝试将 AI 辅助能力与飞控配置流程结合，探索通过自然语言理解飞控参数、解释配置数据以及生成 CLI 命令等功能。

**当前版本不代表完整或稳定的软件。** 项目中的功能、界面和通信逻辑仍可能调整，部分功能可能尚未实现、无法正常工作，或未经充分测试。

---

## 项目状态与安全说明

目前项目主要用于个人开发、技术验证和功能实验。

- **不建议普通用户将其作为日常飞控配置工具。**
- **不要将当前版本用于正式飞行或关键设备。**
- 不保证对所有 Betaflight 固件版本、飞控硬件及操作系统的兼容性。
- 不保证所有界面功能、参数读取、CLI 命令生成或写入流程均正常。
- AI 输出可能存在错误、遗漏或不适用于当前机型的建议。
- 即使 AI 能读取部分配置数据，也不代表它能够准确判断飞行器状态或保证调参安全。

尤其需要注意：错误的飞控参数可能导致飞行器失控、设备损坏或人身伤害。**不要直接执行 AI 生成的命令，也不要仅凭本项目的分析结果进行飞行。** 在功能未经充分验证前，请勿将其连接到准备实际飞行的设备上。

---

## 目前的开发方向

以下是项目正在探索或计划完善的方向，**不代表每项功能都已完成或可用**：

- **飞控数据读取**：尝试通过 MSP 获取 PID、滤波器、电机等配置数据。
- **AI 辅助分析**：将飞控配置上下文提供给兼容 OpenAI API 格式的模型，辅助理解参数。
- **CLI 命令生成**：尝试根据自然语言需求生成 Betaflight CLI 命令。
- **参数说明**：辅助解释常见飞控配置项及其含义。
- **跨平台开发**：探索桌面端与移动端的构建方式。

实际可用范围请以当前代码为准，功能可能随开发进度变化。

---

## AI 服务配置

项目代码中包含对 OpenAI-compatible Chat Completions API 的接入尝试，并预置了部分服务配置，例如：

- OpenAI
- DeepSeek
- 火山引擎
- Ollama（本地服务）

不同服务商的 API 地址、模型名称、鉴权方式和兼容程度可能不同。**不保证上述服务在当前版本中均可正常连接或使用。**

使用在线模型通常需要自行提供 API Key。请勿将 API Key 提交到公开仓库、截图或日志中。

---

## 技术栈

根据当前项目代码，主要涉及：

- Vue 3
- Vite
- Pinia
- Nuxt UI
- Tauri 2 / Rust
- Capacitor
- Betaflight MSP 通信
- OpenAI-compatible API

项目仍在开发中，技术选型和目录结构可能发生变化。

---

## 本地开发

当前项目使用 Node.js 24.x 环境。可先克隆仓库并安装依赖：

```bash
git clone https://github.com/orange508/BetaflightAssistant.git
cd BetaflightAssistant
npm install
```

常用脚本（具体可用性以当前 `package.json` 和本机环境为准）：

```bash
npm run dev
npm run build
npm run lint
npm run test
```

Tauri 和 Android 相关脚本还需要对应的 Rust、系统构建工具、Android SDK 等环境。当前项目尚未保证所有平台均可成功构建或运行。

---

## 项目结构

主要目录包括：

- `src/`：前端应用、组件、状态管理及业务逻辑
- `src/js/`：JavaScript 服务和功能模块
- `src-tauri/`：Tauri / Rust 桌面端工程
- `android/`：Android 工程
- `locales/`：多语言资源
- `resources/`：项目资源
- `scripts/`：开发及构建脚本
- `test/`：测试相关文件

目录和模块可能继续调整。

---

## 参与开发与反馈

欢迎开发者阅读代码、提交 Issue 或 Pull Request。反馈问题时，建议附上：

- 操作系统及版本
- Betaflight 固件版本和飞控型号
- 复现步骤
- 相关错误日志（提交前请删除 API Key、设备标识等敏感信息）

请优先将当前项目视为实验性代码，而不是可直接投入使用的正式发行版。

---

## 下载与发布

GitHub Releases 页面可能包含构建产物，但**出现可下载文件不代表该版本已经稳定、完整或经过飞行安全验证**。在项目状态明确更新为可供测试之前，不建议普通用户安装或使用：

[查看 GitHub Releases](https://github.com/orange508/BetaflightAssistant/releases)

---

## 许可证

本项目使用 [MIT License](LICENSE)，具体以仓库中的许可证文件为准。

---

<p align="center">
  <strong>项目仍在开发中。请谨慎阅读代码与测试，切勿将未经验证的功能用于实际飞行。</strong>
</p>

