# VortexAI v5.0

A **fully free, production-grade AI chat interface** powered by [OpenRouter](https://openrouter.ai). Single HTML file, zero backend, Apache 2.0 licensed.

🚀 **Live**: Open `index.html` in any modern browser  
📦 **Zero Dependencies**: Pure HTML + CSS + JavaScript (uses CDN libraries for convenience)  
🔐 **Privacy-First**: API keys stored locally in localStorage only  
🎨 **Beautiful UI**: Dark theme with Tailwind CSS, responsive design  
💬 **Multi-Model**: Access 100+ free AI models via OpenRouter  
🎯 **Professional Features**: Streaming, code canvas, markdown rendering, RAG-lite, voice input, branching

---

## 📋 Table of Contents

- [Features](#features)
- [Quick Start](#quick-start)
- [Architecture](#architecture)
- [Usage Guide](#usage-guide)
- [Advanced Features](#advanced-features)
- [Settings & Customization](#settings--customization)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Security & Privacy](#security--privacy)
- [Browser Support](#browser-support)
- [Contributing](#contributing)
- [License](#license)
- [Credits](#credits)

---

## ✨ Features

### Core Chat
- **Real-time Streaming**: Watch responses appear in real-time via Server-Sent Events
- **Multi-Model Support**: Browse and switch between 100+ free OpenRouter models
- **Smart Context Management**: Auto-trims older messages to stay within token limits
- **Chat History**: Persistent conversations saved to IndexedDB (local, never synced)
- **Export**: Download chats as Markdown or JSON

### Code Canvas
- **Live Code Editor**: Interactive syntax-highlighted code editor
- **Instant Preview**: HTML/CSS/JavaScript rendered in sandboxed iframe
- **Code Block Integration**: Run code directly from AI responses
- **Download Code**: Save generated code as files with auto-detected extensions

### Advanced
- **RAG-Lite**: Attach `.txt`, `.md`, code files as context (Web API integration)
- **Voice Input**: Convert speech to text using Web Speech API
- **Conversation Branching**: Fork messages at any point, explore alternatives
- **System Prompts**: Core AI identity + custom user instructions
- **Regenerate**: Retry the last AI response with one click

### UI/UX
- **Dark Theme**: Eye-friendly dark background with accent colors
- **6 Themes**: Default, Purple, Teal, Rose, Amber, Cyan
- **2 Fonts**: Sans (Inter) or Monospace (JetBrains Mono)
- **Responsive**: Mobile, tablet, desktop optimized
- **Compact Mode**: Tighter message spacing for more conversation

---

## 🚀 Quick Start

### Option 1: Online
Simply visit the GitHub Pages deployment (if available) or open the HTML file directly.

### Option 2: Local
1. Clone the repository:
   ```bash
   git clone https://github.com/zelvior/chatbot.git
   cd chatbot
   ```

2. Open `index.html` in your browser:
   ```bash
   open index.html
   # or on Windows:
   start index.html
   # or on Linux:
   xdg-open index.html
   ```

3. Accept the terms & conditions
4. Get a free OpenRouter API key: [https://openrouter.ai/keys](https://openrouter.ai/keys)
5. Paste your key in **Settings** (Ctrl+Shift+S)
6. Start chatting!

---

## 🏗️ Architecture

### Single-File Design
VortexAI is intentionally built as **one HTML file** containing:
- **HTML**: Full UI structure (header, sidebar, chat, canvas, modals)
- **CSS**: ~550 lines of styling + Tailwind for utilities
- **JavaScript**: ~1000+ lines of vanilla JS (no frameworks)

### External Dependencies (CDN)
```
- Tailwind CSS (styling)
- Marked (markdown rendering)
- DOMPurify (XSS protection)
- Highlight.js (syntax highlighting)
- Google Fonts (Syne, JetBrains Mono, Inter)
```

### State Management
- **localStorage**: API key, settings, theme, UI preferences
- **IndexedDB**: Chat history (persistent, never synced to server)
- **In-Memory**: Current conversation, attachments, UI state

### API Integration
- **OpenRouter API** (`https://openrouter.ai/api/v1/chat/completions`)
- **Server-Sent Events (SSE)** for real-time streaming
- No backend required; all requests are client-side

---

## 📖 Usage Guide

### Chatting
1. Type your message in the input bar
2. Press **Enter** (or click Send)
3. Watch the AI response stream in real-time
4. Press **Escape** to stop generation

### Model Selection
- Click the model name in the header to open **Models Library**
- Search, filter by category (Text, Vision, Coding, etc.)
- Click to select; recently used models are pinned

### Code Canvas
1. Ask the AI to write code (HTML, JavaScript, Python, etc.)
2. Code blocks appear with a **▶ Run** button (for web languages)
3. Click to open the **Canvas Panel**
4. **Code Tab**: View syntax-highlighted code
5. **Editor Tab**: Edit and instantly update preview
6. **Preview Tab**: See live rendering
7. **Copy** or **Save** to download

### System Prompts
- **Core Identity**: Fixed system prompt (VortexAI's role, capabilities)
- **Custom Instructions**: Add your own via the System Prompt button (Ctrl+Shift+P)
- Custom instructions are appended to the core prompt for each request

### File Attachments (RAG-Lite)
1. Click the **📎 Attach** button
2. Select one or more code/text files
3. Files are read and included in the next message
4. Remove individual files with the **×** button

### Voice Input
1. Click the 🎤 **Voice** button
2. Speak clearly (browser shows recording indicator)
3. Speech is converted to text and inserted into the input
4. Press Send to chat

---

## 🎯 Advanced Features

### Conversation Branching
- Hover over any message to see action buttons
- **Fork**: Create an alternative response branch
- Branches are stored in memory; refresh the page to reset

### Regenerate
- At the bottom (Token Bar), click **Regen** to retry the last AI response
- Useful for getting different answers or longer completeness

### Export & Share
1. Click **Export Chat** (Ctrl+E)
2. Choose **Markdown** (human-readable) or **JSON** (structured)
3. Download for archiving, sharing, or importing elsewhere

### Temperature Control
- **0 (Precise)**: Deterministic, factual responses
- **0.7 (Balanced)**: Default; creative yet coherent
- **2 (Creative)**: Maximum randomness; wild ideas

### Context Management
- Set **Max Context Messages** (default: 40)
- Older messages beyond this limit are trimmed to save tokens
- Token count is estimated and shown in the Token Bar

---

## ⚙️ Settings & Customization

Open **Settings** (⚙️ or Ctrl+Shift+S):

| Setting | Default | Purpose |
|---------|---------|---------|
| OpenRouter API Key | — | Required for API access |
| Temperature | 0.7 | Response creativity |
| Max Context Messages | 40 | Conversation history depth |
| Accent Theme | Default (Purple) | UI color scheme |
| UI Font | Sans | Font for interface text |
| Compact Messages | Off | Reduce spacing between messages |
| Auto-scroll | On | Auto-scroll to new messages during streaming |

All settings are saved to localStorage automatically.

---

## ⌨️ Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| New Chat | Ctrl+Shift+N |
| Model Picker | Ctrl+K |
| Toggle Sidebar | Ctrl+B |
| Send Message | Enter |
| New Line | Shift+Enter |
| Stop Generation | Escape |
| Focus Input | Ctrl+/ |
| System Prompt | Ctrl+Shift+P |
| Export Chat | Ctrl+E |
| Settings | Ctrl+Shift+S |

---

## 🔐 Security & Privacy

### Local-First Architecture
- **No Backend**: All requests go directly from browser → OpenRouter API
- **No Tracking**: No analytics, telemetry, or cookies
- **No Logging**: VortexAI never stores conversations server-side

### API Key Safety
- Stored in **localStorage only** (not sent to VortexAI servers)
- Never logged or transmitted to any third party
- Clear before sharing your device

### Data Privacy
- Conversations are sent to **OpenRouter** and the selected model provider
- Refer to [OpenRouter Privacy Policy](https://openrouter.ai/privacy)
- Chat history in IndexedDB is **device-local only**

### XSS Protection
- All user input and AI output sanitized via **DOMPurify**
- Code canvas runs in a **sandboxed iframe** (no access to main DOM)
- Markdown rendered safely without executing untrusted scripts

---

## 🌐 Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 90+ | ✅ Fully Supported |
| Firefox | 88+ | ✅ Fully Supported |
| Safari | 14+ | ✅ Fully Supported |
| Edge | 90+ | ✅ Fully Supported |
| Opera | 76+ | ✅ Fully Supported |

**Features Requiring Modern APIs:**
- **Service Workers**: Required for offline history (if implemented)
- **Web Speech API**: Voice input (Safari has limited support)
- **IndexedDB**: Persistent chat history

---

## 🛠️ Contributing

Contributions are welcome! Areas of interest:

- Bug fixes and optimizations
- New themes or UI improvements
- Additional model integrations
- Better voice recognition
- i18n (internationalization)

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Make changes to `index.html`
4. Test thoroughly in multiple browsers
5. Submit a pull request

---

## 📜 License

**Apache License 2.0**

VortexAI is open-source and free for personal and commercial use. See [LICENSE](./LICENSE) for details.

### Summary
- ✅ Commercial Use
- ✅ Modification
- ✅ Distribution
- ✅ Private Use
- ❌ Warranty (provided "as is")
- ❌ Liability

---

## 👨‍💻 Credits

**Creator**: [Zelvior](https://github.com/zelvior) (Pakistan)  
**Version**: 5.0  
**Release Year**: 2025  
**API Provider**: [OpenRouter](https://openrouter.ai) (free tier)

### Technologies Used
- **Marked**: Markdown parsing & rendering
- **Highlight.js**: Syntax highlighting
- **DOMPurify**: XSS sanitization
- **Tailwind CSS**: Utility-first styling
- **Google Fonts**: Typography (Syne, Inter, JetBrains Mono)

---

## 📝 Changelog

### v5.0 (Current)
- ✨ Voice input via Web Speech API
- ✨ File attachments (RAG-Lite)
- ✨ Interactive code editor in canvas
- ✨ Download code blocks directly
- ✨ Conversation branching & forking
- ✨ Separable core system prompt + custom instructions
- 🎨 Improved UI with custom system bar
- 🔧 Optimized streaming & token counting
- 🐛 Various bug fixes

### v4.0
- ✨ Context window trimming
- ✨ Regenerate button
- ✨ Export chat as Markdown/JSON
- ✨ Scroll-to-bottom during generation
- ✨ Per-message copy/regenerate actions
- ✨ Themes (Purple, Teal, Rose, Amber, Cyan)
- ✨ Auto-scroll toggle

### v3.0 & Earlier
- Core chat interface
- Model selection
- Real-time streaming
- Settings & customization

---

## 📞 Support

For issues, feature requests, or questions:
1. Check the [GitHub Issues](https://github.com/zelvior/chatbot/issues)
2. Create a new issue with details
3. Follow the code of conduct

---

## 🎓 Learning Resources

- **OpenRouter Docs**: https://openrouter.ai/docs
- **Marked.js Docs**: https://marked.js.org
- **Highlight.js**: https://highlightjs.org
- **MDN Web Docs**: https://developer.mozilla.org

---

## ⚠️ Disclaimer

VortexAI is provided **"as is"** without warranty. Users are responsible for:
- Verifying AI-generated content
- Complying with OpenRouter terms of service
- Safeguarding their API keys
- Legal use of the software

The creators of VortexAI are **not liable** for any damages, data loss, or misuse of the interface.

---

**Made with ❤️ by Zelvior · Pakistan · 2025**
