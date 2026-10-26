ZeroScript - Free AI Agent for Roblox Studio — Fork

«⚠️ Important: This fork is no longer considered a reliable solution.

After more testing and feedback from users, it became clear that this fork only works partially. Multiple people reported that it still does not work correctly, and DeepSeek rate limits / temporary bans can still occur.

I originally created this fork to improve DeepSeek reliability, but the remaining issues turned out to be more complicated than expected.»

🚀 Looking for a better alternative?

I eventually decided to build my own Roblox AI agent from scratch: "LuaPilot" (https://github.com/MaciekGos/LuaPilot).

LuaPilot is my current project and the recommended alternative to this fork.

👉 "GitHub: MaciekGos/LuaPilot" (https://github.com/MaciekGos/LuaPilot)

LuaPilot was created after I realized that simply patching ZeroScript's DeepSeek handling was not enough to reliably solve the underlying problems.

---

«⚠️ This is a fork of "ZeroScript - Free AI Agent for Roblox Studio" (https://github.com/sebattfg/ZeroScript-Free).»

This fork contains additional improvements that were mainly intended to improve DeepSeek agent reliability, including automatic rate-limit recovery and improved "<ds_safety>" rendering.

"Platform" (https://img.shields.io/badge/platform-Windows%20%7C%20macOS-lightgrey)
"License" (https://img.shields.io/badge/license-GPL--3.0-blue)

ZeroScript is a free browser extension that turns ChatGPT, DeepSeek, Gemini, Kimi, GLM, Qwen, Arena or Meta AI into a Roblox Studio AI agent.

Control Roblox Studio with AI directly from your browser — read/edit scripts, run Luau, generate assets, all from a normal AI chat. No API key, no terminal, no coding needed.

🔧 Changes in this fork

This fork originally focused on improving DeepSeek reliability:

- DeepSeek rate-limit recovery: detects "Messages too frequent. Try again later.", stops the agent loop, saves its state, disconnects and reconnects the Bridge, reloads the page and resumes the session.
- Runaway protection: prevents endless recovery attempts when DeepSeek repeatedly returns the rate-limit notice.
- "<ds_safety>" rendering: converts DeepSeek safety notices into a readable ⚠ Safety notice box instead of displaying the raw tags.
- Streaming support: handles safety notices while DeepSeek is still generating a response, including unclosed and multi-paragraph notices.
- DOM-safe rendering: hides the original safety content instead of removing it, allowing the renderer to survive React re-renders.
- Reasoning protection: ignores safety notices inside the reasoning area.

⚠️ Current status

Despite these changes, the fork does not completely solve the DeepSeek issues.

During testing and after receiving reports from multiple users, it became clear that:

- the fork only works partially for some users;
- DeepSeek rate limits can still happen;
- users can still experience temporary restrictions/bans;
- the recovery system does not always prevent another request from triggering a restriction;
- behavior can vary between users and sessions.

In one of my own tests, DeepSeek still temporarily prevented me from sending messages for several minutes despite the protection.

Because of this, I do not recommend relying on this fork as a guaranteed way to avoid DeepSeek rate limits or bans.

The original goal was to find and fix the exact cause of these problems, but after further testing it became clear that the issue could not be reliably solved just by patching ZeroScript's existing agent loop.

🧪 Testing

The fork changes were tested with:

- "node --check"
- jsdom DeepSeek DOM captures
- streaming and closed "<ds_safety>" cases
- multi-paragraph safety notices
- real DOM elements
- reasoning-area handling
- rate-limit detection

The individual fixes work in the tested cases, but they do not guarantee that DeepSeek will not rate-limit or restrict an account.

---

🚀 LuaPilot — my new project

Because of the limitations I encountered while working on this fork, I started developing my own Roblox AI agent:

"LuaPilot" (https://github.com/MaciekGos/LuaPilot)

LuaPilot is not simply another patch for ZeroScript. It is a separate project that I am developing with the goal of having more control over how the AI agent communicates with Roblox Studio and handles its workflow.

If you came here because ZeroScript or this fork is not working properly for you, I recommend trying LuaPilot instead.

👉 "Go to LuaPilot →" (https://github.com/MaciekGos/LuaPilot)

---

Original project

ZeroScript is a free browser extension that turns ChatGPT, DeepSeek, Gemini, Kimi, GLM, Qwen, Arena or Meta AI into a Roblox Studio AI agent.

Control Roblox Studio with AI directly from your browser — read/edit scripts, run Luau, generate assets, all from a normal AI chat. No API key, no terminal, no coding needed.

«🌐 Website: "zerodev.tools/zeroscript" (https://zerodev.tools/zeroscript) — the free Lemonade.gg / Luamotion alternative for building Roblox games with AI.»

Eight AI providers are supported: DeepSeek (chat.deepseek.com, recommended), ChatGPT (chatgpt.com), Google Gemini (gemini.google.com), Kimi (kimi.ai, Moonshot AI), GLM (chat.z.ai, Z.ai), Qwen (chat.qwen.ai), Arena (arena.ai, a multi-model playground) and Meta AI (meta.ai).

«💬 Stuck? Join the "Discord community" (https://discord.gg/9aNyZsMWcb) to get help, share feedback, and follow updates.»

See the original repository for the complete setup guide, feature list and historical changelog.

License

This fork remains licensed under GNU GPL v3, in accordance with the original project.

Credit: the idea for connecting other MCP servers (Blender, Sketchfab, etc.) alongside Roblox Studio came from "javnpa" (https://github.com/javnpa).

Credit: macOS/Linux support contributed by "archivealf" (https://github.com/archivealf).
