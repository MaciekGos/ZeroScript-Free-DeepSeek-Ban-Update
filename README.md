# ZeroScript - Free AI Agent for Roblox Studio — Fork

> ⚠️ **This is a fork of [ZeroScript - Free AI Agent for Roblox Studio](https://github.com/sebattfg/ZeroScript-Free).**

This fork contains additional improvements focused mainly on **DeepSeek agent reliability**, including automatic rate-limit recovery and improved `<ds_safety>` rendering.

![GitHub stars](https://img.shields.io/github/stars/sebattfg/ZeroScript-Free?style=social)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-lightgrey)
![License](https://img.shields.io/badge/license-GPL--3.0-blue)

**ZeroScript** is a free browser extension that turns ChatGPT, DeepSeek, Gemini, Kimi, GLM, Qwen, Arena or Meta AI into a Roblox Studio AI agent.  
Control Roblox Studio with AI directly from your browser - read/edit scripts, run Luau, generate assets, all from a normal AI chat. No API key, no terminal, no coding needed.

## 🔧 Changes in this fork

- **DeepSeek rate-limit recovery:** detects `Messages too frequent. Try again later.`, stops the agent loop, saves its state, disconnects and reconnects the Bridge, reloads the page and resumes the session.
- **Runaway protection:** prevents endless recovery attempts when DeepSeek repeatedly returns the rate-limit notice.
- **`<ds_safety>` rendering:** converts DeepSeek safety notices into a readable **⚠ Safety notice** box instead of displaying the raw tags.
- **Streaming support:** handles safety notices while DeepSeek is still generating a response, including unclosed and multi-paragraph notices.
- **DOM-safe rendering:** hides the original safety content instead of removing it, allowing the renderer to survive React re-renders.
- **Reasoning protection:** ignores safety notices inside the reasoning area.

### Testing

The fork changes were tested with `node --check`, jsdom DeepSeek DOM captures, streaming and closed `<ds_safety>` cases, multi-paragraph notices, real DOM elements, reasoning-area handling and rate-limit detection.

The complete live reload → reconnect → resume flow has not yet been tested in a full production DeepSeek session.

---

[**Original ZeroScript README and documentation →**](https://github.com/sebattfg/ZeroScript-Free)

---

## Original project

**ZeroScript** is a free browser extension that turns ChatGPT, DeepSeek, Gemini, Kimi, GLM, Qwen, Arena or Meta AI into a Roblox Studio AI agent.  
Control Roblox Studio with AI directly from your browser - read/edit scripts, run Luau, generate assets, all from a normal AI chat. No API key, no terminal, no coding needed.

> 🌐 **Website: [zerodev.tools/zeroscript](https://zerodev.tools/zeroscript)** the free Lemonade.gg / Luamotion alternative for building Roblox games with AI.

Eight AI providers are supported: **DeepSeek** (chat.deepseek.com, recommended), **ChatGPT** (chatgpt.com), **Google Gemini** (gemini.google.com), **Kimi** (kimi.ai, Moonshot AI), **GLM** (chat.z.ai, Z.ai), **Qwen** (chat.qwen.ai), **Arena** (arena.ai, a multi-model playground) and **Meta AI** (meta.ai).

> 💬 **Stuck? Join the [Discord community](https://discord.gg/9aNyZsMWcb)** get help, share feedback, and follow updates.

See the original repository for the complete setup guide, feature list and historical changelog.

## License

This fork remains licensed under **GNU GPL v3**, in accordance with the original project.

Credit: the idea for connecting other MCP servers (Blender, Sketchfab, etc.) alongside Roblox Studio came from [javnpa](https://github.com/javnpa).

Credit: macOS/Linux support contributed by [archivealf](https://github.com/archivealf).
