# TypeNo - 语音输入工具

🎤 按下热键说话，文字自动输入到任何地方。

跨平台语音输入工具，原版为macOS设计 [TypeNo](https://github.com/marswaveai/TypeNo)。

---

## 📥 下载即用（推荐）

**无需安装任何东西！**

1. 进入 [Releases](https://github.com/你的用户名/typeno-cross/releases) 页面
2. 下载 `typeno-cross.exe`
3. 双击运行

---

## ⌨️ 使用方法

1. 按 **Ctrl+Shift+R** 开始录音（窗口显示 "● Recording..."）
2. 对着麦克风说话
3. 再按 **Ctrl+Shift+R** 停止，转写文字自动粘贴到光标位置
4. 或等待60秒自动停止

---

## 🔧 技术用户 - 从源码构建

### 支持平台

- ✅ Windows 10/11
- ✅ macOS 12+
- ✅ Linux

### 环境要求

- [Node.js](https://nodejs.org)
- [Rust](https://rustup.rs) 1.70+
- 语音引擎：`npm install -g @marswave/coli`

### 构建步骤

```bash
# 安装依赖
npm install

# 安装语音引擎
npm install -g @marswave/coli

# 开发模式运行
npm run dev

# 生产环境构建
npm run tauri build
```

### 工作原理

1. 按 **Ctrl+Shift+R** 开始录音
2. 说话
3. 再按 **Ctrl+Shift+R** 停止，文字自动粘贴

### 技术栈

- **Tauri 2** — 桌面应用框架
- **TypeScript** — 前端逻辑
- **Rust + cpal** — 音频采集
- **Coli ASR** — 本地语音识别

### 项目结构

```
typeno-cross/
├── src/                    # 前端源码
├── src-tauri/              # Rust后端
├── package.json
└── README.md
```

### 热键设置

修改 `src/platform/hotkey.ts`：
```ts
await registerHotkey("Control", onToggle); // Windows/Linux
await registerHotkey("Command", onToggle); // macOS
```

## 许可证

GNU General Public License v3.0
