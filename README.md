# VortexAI v6.0

**A production-grade, fully-featured AI chat interface powered by OpenRouter.**

🚀 **Live Preview**: https://zelvior.github.io/chatbot/  
📦 **Single HTML File**: Zero backend, zero build process, zero dependencies  
🔐 **Privacy-First**: Your API key never leaves your device  
🎨 **Professional UI**: Dark theme, responsive design, multiple customization options  
💬 **100+ Models**: Access free AI models via OpenRouter (no sign-up required)

---

## 📋 Table of Contents

- [Features](#features)
- [Quick Start](#quick-start)
- [Live Preview](#live-preview)
- [Architecture & Design](#architecture--design)
- [Usage Guide](#usage-guide)
- [Advanced Features](#advanced-features)
- [Settings & Customization](#settings--customization)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Security & Privacy](#security--privacy)
- [Browser Support](#browser-support)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)
- [Credits](#credits)

---

## ✨ Features

### Core Chat Experience
- **Real-Time Streaming**: Watch AI responses appear in real-time via Server-Sent Events (SSE)
- **100+ Free Models**: Access Claude, GPT-4, Llama, Mistral, and more via OpenRouter
- **Instant Model Switching**: Switch between models without losing conversation context
- **Persistent Chat History**: Local storage with IndexedDB (device-only, never synced)
- **Smart Context Management**: Automatic trimming of older messages to stay within token limits
- **Export & Share**: Download chats as Markdown or JSON for archiving and sharing

### Code Canvas
- **Live Code Editor**: Interactive editor with syntax highlighting via Highlight.js
- **Instant Preview**: Render HTML/CSS/JavaScript in a sandboxed iframe
- **Direct Code Execution**: Run code blocks from AI responses with a single click
- **Code Block Integration**: Copy, download, or edit code directly
- **Multiple Languages**: Support for HTML, CSS, JavaScript, Python, and more

### Advanced Capabilities
- **File Attachments (RAG-Lite)**: Attach `.txt`, `.md`, and code files as context
- **Voice Input**: Convert speech to text using the Web Speech API
- **Conversation Branching**: Fork messages to explore alternative responses
- **System Prompts**: Separable core identity + custom user instructions
- **Regenerate**: Retry the last AI response with different parameters
- **Thinking Steps**: View AI reasoning process (for capable models)
- **Web Search**: Enable web search context for current information

### UI/UX
- **8+ Color Themes**: Default (Purple), Teal, Rose, Amber, Cyan, Emerald, Sky, Fuchsia
- **2 Font Options**: Sans (Inter) or Monospace (JetBrains Mono)
- **Light Mode**: Eye-friendly light theme included
- **Fully Responsive**: Desktop, tablet, mobile-optimized
- **Compact Mode**: Tighter spacing for power users
- **Command Palette**: Quick access to all features (Ctrl+P)
- **Dark Theme Variants**: Enjoy the beautiful dark UI

### Gamification & Social
- **XP System**: Earn points for chat interactions
- **Achievements**: Unlock badges for various milestones
- **Level Progression**: Track your user level
- **XP Store**: Purchase cosmetic items with earned points
- **Chat Statistics**: View analytics on your conversations

---

## 🚀 Quick Start

### Option 1: Use Online (Recommended)
Simply visit the live preview link below—no installation needed.

**👉 https://zelvior.github.io/chatbot/**

### Option 2: Clone & Run Locally

```bash
# Clone the repository
git clone https://github.com/zelvior/chatbot.git
cd chatbot

# Open index.html directly in your browser
open index.html
# On Windows:
start index.html
# On Linux:
xdg-open index.html
```

### First-Time Setup
1. **Accept Terms**: Read and accept the terms & conditions
2. **Get an API Key**: 
   - Visit https://openrouter.ai/keys (free tier available)
   - Copy your API key (no sign-up required for basic usage)
3. **Paste Your Key**: Open Settings (⚙️ or Ctrl+Shift+S) and paste your key
4. **Start Chatting**: Begin your conversation!

---

## 🌐 Live Preview

**Preview URL**: https://zelvior.github.io/chatbot/

The live preview is always up-to-date with the latest version. No installation, no server, no tracking.

---

## 🏗️ Architecture & Design

### Single-File Design Philosophy
VortexAI is intentionally built as **one HTML file** containing everything:

- **HTML**: Full UI structure (header, sidebar, chat panel, modals, code canvas)
- **CSS**: 700+ lines of responsive styling (Tailwind + custom)
- **JavaScript**: 5000+ lines of vanilla JS (no frameworks, no build tools)

### Why Single File?
✅ **Simplicity**: Download, open, use  
✅ **Portability**: Works everywhere (local, USB, GitHub Pages)  
✅ **Privacy**: Never connects to any backend  
✅ **Offline-First**: All logic runs in your browser  

### External Dependencies (CDN)
These are loaded from CDN for convenience (optional, can be self-hosted):

```
- Tailwind CSS (styling framework)
- Marked.js (markdown parsing)
- DOMPurify (XSS protection)
- Highlight.js (syntax highlighting)
- Google Fonts (typography)
```

### State Management
- **localStorage**: API key, settings, theme, UI preferences
- **IndexedDB**: Full chat history (local, never synced)
- **sessionStorage**: Temporary data (attachments, branches)
- **In-Memory**: Current conversation, UI state

### API Integration
- **Endpoint**: `https://openrouter.ai/api/v1/chat/completions`
- **Protocol**: REST + Server-Sent Events (streaming)
- **Authentication**: Bearer token (your API key)
- **No Backend**: Direct browser → OpenRouter

### Security Features
- **XSS Protection**: DOMPurify sanitizes all user input and AI output
- **Sandboxed Code Canvas**: Code runs in isolated iframe with no DOM access
- **Client-Side Only**: No server-side logging or tracking
- **API Key**: Stored locally, never transmitted to third parties

---

## 📖 Usage Guide

### Basic Chatting
1. Type your message in the input bar
2. Press **Enter** to send (or click Send button)
3. Watch the AI response stream in real-time
4. Press **Escape** to stop generation mid-stream

### Selecting a Model
1. Click the model name in the header (shows current model)
2. Browse the **Models Library**
3. Filter by category (Free, Fast, Quality, Vision, Coding, etc.)
4. Click to select (changes take effect immediately)
5. Recently used models appear at the top

### Using the Code Canvas
1. Ask the AI to write code (HTML, JavaScript, Python, etc.)
2. Code blocks appear with a **▶ Run** button
3. Click **Run** to open the Canvas Panel
4. **Code Tab**: View syntax-highlighted source
5. **Editor Tab**: Edit code live with instant preview
6. **Preview Tab**: See rendered output
7. **Copy** or **Download** to save locally

### Attaching Files (RAG)
1. Click the **📎 Attach** button
2. Select one or more files (`.txt`, `.md`, code files)
3. Files appear as pills below the input
4. Remove individual files with **×** button
5. Send your message—files are included as context

### Voice Input
1. Click the **🎤 Voice** button
2. Speak clearly (browser shows recording indicator)
3. Speech is transcribed and inserted into input
4. Press Enter to send (or review and edit first)
5. Works best in quiet environments

### System Prompts
- **Core Prompt**: Fixed identity (VortexAI's role & capabilities)
- **Custom Instructions**: Your own rules appended to each request
- Toggle with **Ctrl+Shift+P** or Settings button
- Changes take effect on next message

### Conversation Branching
1. Hover over any message
2. Click the **Fork** button
3. Creates an alternative branch from that point
4. Switch between branches with navigation buttons
5. Branches exist in-memory; refresh to reset

### Regenerate Response
- Click the **Regen** button in the Token Bar (bottom of chat)
- Retries the last AI response (useful for different answers)
- Maintains context, only regenerates the final message

### Export & Share
1. Click **Export Chat** (Ctrl+E)
2. Choose format:
   - **Markdown**: Human-readable, formatted nicely
   - **JSON**: Structured data, can be imported back
3. Download for archiving or sharing

---

## 🎯 Advanced Features

### Smart Context Management
- **Max Context Messages**: Default 40 (configurable)
- **Auto-Trimming**: Older messages removed to stay within token limits
- **Token Counter**: Shows current usage vs. limits
- **Visual Indicator**: Accent ring shows context load

### Temperature Control
- **0 (Precise)**: Deterministic, factual responses
- **0.7 (Balanced)**: Default; creative yet coherent
- **2 (Creative)**: Maximum randomness; experimental ideas
- **Slider**: Fine-tune between 0 and 2

### Web Search
- **Toggle**: Ctrl+Shift+W or Web Search button
- **Enhanced Responses**: Access to current information
- **Inline Sources**: References appear in responses
- **Limited Availability**: Only works with models that support it

### Deep Thinking (Reasoning Models)
- **Toggle**: Ctrl+Shift+I
- **Extended Reasoning**: Watch the AI think through problems
- **Visible Steps**: See intermediate thinking process
- **Model-Specific**: Only available with reasoning models (o1, r1, etc.)

### Multi-Model Comparison
- **Side-by-Side**: Compare responses from multiple models
- **Same Prompt**: Send to 2-4 models simultaneously
- **Fast Analysis**: See different perspectives instantly
- **Access**: Click ⚖️ in sidebar or use Command Palette

### Chat Analytics
- **Statistics**: View message count, tokens, average response length
- **Time Tracking**: See when you chatted and for how long
- **Popular Models**: Statistics on your most-used models
- **Export Data**: Download analytics as JSON/CSV

### Monaco Editor
- **Advanced Editing**: Full-featured code editor modal
- **Syntax Highlighting**: 100+ languages supported
- **Find & Replace**: Professional editor features
- **Language Selection**: Auto-detect or manual selection
- **Access**: Ctrl+M or 📝 button in sidebar

---

## ⚙️ Settings & Customization

Open **Settings** (⚙️ button or Ctrl+Shift+S):

### API Configuration
| Setting | Default | Purpose |
|---------|---------|---------|
| **OpenRouter API Key** | — | Required for API access |
| **Custom API Endpoint** | openrouter.ai | Point to alternative providers |
| **Model Fallback** | Auto | Auto-select if default unavailable |

### Response Parameters
| Setting | Default | Purpose |
|---------|---------|---------|
| **Temperature** | 0.7 | Response creativity (0-2) |
| **Max Tokens** | 2000 | Maximum response length |
| **Top P** | 1.0 | Diversity control (0-1) |
| **Presence Penalty** | 0 | Encourage new topics |
| **Frequency Penalty** | 0 | Reduce repetition |

### Context Settings
| Setting | Default | Purpose |
|---------|---------|---------|
| **Max Context Messages** | 40 | How many messages to keep |
| **System Prompt** | VortexAI default | AI identity & instructions |
| **Custom Instructions** | — | Your additional rules |

### UI Customization
| Setting | Default | Purpose |
|---------|---------|---------|
| **Theme** | Default (Purple) | Color scheme |
| **Font** | Sans (Inter) | UI font family |
| **Light Mode** | Off | Light vs. dark theme |
| **Compact Mode** | Off | Reduce message spacing |
| **Auto-Scroll** | On | Scroll to new messages |

### Advanced Options
| Setting | Default | Purpose |
|---------|---------|---------|
| **Voice Language** | English | Speech recognition language |
| **Cache Size** | 100 MB | Local storage limit |
| **Export Format** | Markdown | Default export type |
| **Privacy Mode** | Off | Don't save chat history |

---

## ⌨️ Keyboard Shortcuts

| Action | Shortcut | Description |
|--------|----------|-------------|
| **Send Message** | `Enter` | Send current message |
| **New Line** | `Shift+Enter` | Line break in input |
| **New Chat** | `Ctrl+Shift+N` | Start fresh conversation |
| **Model Picker** | `Ctrl+K` | Open model selection |
| **Settings** | `Ctrl+Shift+S` | Open settings modal |
| **Toggle Sidebar** | `Ctrl+B` | Show/hide chat history |
| **System Prompt** | `Ctrl+Shift+P` | Edit system prompt |
| **Export Chat** | `Ctrl+E` | Download conversation |
| **Stop Generation** | `Escape` | Cancel AI response |
| **Find in Chat** | `Ctrl+F` | Search chat history |
| **Command Palette** | `Ctrl+P` | Quick access menu |
| **Keyboard Shortcuts** | `Ctrl+Shift+K` | Show this list |
| **Achievements** | `Ctrl+Shift+A` | View badges & XP |
| **XP Store** | `Ctrl+Shift+S` | Purchase cosmetics |
| **Focus Mode** | `Ctrl+Shift+F` | Timer mode |
| **Web Search** | `Ctrl+Shift+W` | Toggle web search |
| **Deep Thinking** | `Ctrl+Shift+I` | Toggle reasoning |
| **Personas** | `Ctrl+Shift+R` | Switch AI personality |
| **Monaco Editor** | `Ctrl+M` | Open code editor |
| **Console** | `Ctrl+```` | Toggle developer console |
| **UI Customizer** | `Ctrl+Shift+U` | Customize interface |
| **Notes** | `Ctrl+Shift+O` | Quick notes panel |

---

## 🔐 Security & Privacy

### Local-First Architecture
✅ **No Backend**: All requests go directly from browser → OpenRouter API  
✅ **No Tracking**: No analytics, telemetry, cookies, or third-party scripts  
✅ **No Logging**: VortexAI never stores conversations server-side  
✅ **No Ads**: Completely ad-free experience  

### API Key Safety
- **Stored Locally**: IndexedDB/localStorage only (not on servers)
- **Never Transmitted**: Key never sent to VortexAI or any third party
- **Easily Cleared**: Settings provide easy key deletion
- **Revocable**: Invalidate key on OpenRouter anytime

### Data Privacy
- **Direct Routing**: Conversations sent only to OpenRouter/model providers
- **Model Privacy**: Refer to individual model provider policies
- **Local History**: Chat history stays on your device
- **Device-Only**: Never synced to cloud or servers
- **GDPR Compliant**: No personal data collection

### XSS & Injection Protection
- **DOMPurify**: All user input and AI output sanitized
- **Sandboxed Canvas**: Code runs in isolated iframe (no DOM access)
- **No Eval**: Code never evaluated directly
- **Safe Markdown**: Rendered safely without script execution
- **Input Validation**: All inputs validated before use

### Secure Coding Practices
- **No Dangerous APIs**: Avoiding `innerHTML`, `eval()`, `new Function()`
- **Content Security Policy**: Strict CSP headers recommended
- **HTTPS Only**: Use TLS for all connections
- **Regular Audits**: Code reviewed for security issues

### Disclaimers
⚠️ **As-Is Warranty**: Provided without guarantee or liability  
⚠️ **Verify Outputs**: Always verify critical AI-generated content  
⚠️ **Model Providers**: Responsible for model policies and safety  
⚠️ **Your Key**: Never share your OpenRouter API key  

---

## 🌐 Browser Support

| Browser | Version | Status | Notes |
|---------|---------|--------|-------|
| **Chrome** | 90+ | ✅ Full Support | Recommended |
| **Firefox** | 88+ | ✅ Full Support | Excellent |
| **Safari** | 14+ | ✅ Full Support | Limited voice |
| **Edge** | 90+ | ✅ Full Support | Chromium-based |
| **Opera** | 76+ | ✅ Full Support | Chromium-based |
| **Mobile Chrome** | Latest | ✅ Full Support | Touch-optimized |
| **Mobile Safari** | iOS 14+ | ✅ Full Support | Limited voice |

### Features Requiring Modern APIs
- **IndexedDB**: Persistent chat history
- **Web Speech API**: Voice input (Safari limited)
- **Service Workers**: Offline support (future)
- **ResizeObserver**: Responsive canvas
- **Fetch Streams**: SSE streaming

### Known Limitations
- **Safari**: Limited Web Speech API support
- **Mobile**: Some features hidden on small screens
- **Firefox**: Optional cosmetics may display differently
- **IE11**: Not supported (use modern browser)

---

## 🛠️ Development

### Project Structure
```
index.html          # Everything in one file!
├── <head>
│   ├── Meta tags
│   ├── CDN imports (Tailwind, Marked, etc.)
│   └── ~700 lines of CSS
├── <style> tags    # Additional responsive & component styles
└── <body>
    ├── Modals
    ├── Header
    ├── Sidebar
    ├── Chat panel
    ├── Canvas panel
    └── ~5000 lines of vanilla JavaScript
```

### Building Locally
No build process needed! Just:
1. Edit `index.html`
2. Open in browser
3. Test thoroughly
4. Commit

### Adding New Features
1. Add HTML in appropriate section
2. Add CSS (global or component-scoped)
3. Add JavaScript functions
4. Test across browsers
5. Update README
6. Submit PR

### Code Organization (JavaScript)
- **Initialization**: Load settings, history on page load
- **Event Listeners**: Button clicks, keyboard shortcuts
- **API Integration**: OpenRouter communication
- **UI Updates**: DOM manipulation, animations
- **Utilities**: Helpers for parsing, formatting, storage

---

## 🤝 Contributing

We welcome contributions! Areas of interest:

✨ **Features**
- New themes or UI improvements
- Better accessibility
- i18n (internationalization)
- New model integrations

🐛 **Bug Fixes**
- Performance optimizations
- Cross-browser compatibility
- Accessibility improvements

📚 **Documentation**
- Usage examples
- Feature tutorials
- Troubleshooting guides

### How to Contribute
1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/your-feature`
3. **Make** your changes to `index.html`
4. **Test** thoroughly in multiple browsers
5. **Commit**: `git commit -m "Add feature: description"`
6. **Push**: `git push origin feature/your-feature`
7. **Submit** a Pull Request with description

### Code Guidelines
- Keep code well-commented
- Use meaningful variable names
- Test on mobile and desktop
- Follow existing code style
- Update README if needed

---

## 📜 License

**Apache License 2.0**

VortexAI is open-source and free for personal and commercial use.

### What You Can Do ✅
- ✅ Use commercially
- ✅ Modify and distribute
- ✅ Use privately
- ✅ Sublicense
- ✅ Place warranty disclaimers

### What You Can't Do ❌
- ❌ Remove license notices
- ❌ Hold authors liable
- ❌ Claim warranty/support
- ❌ Use trademarks without permission

See [LICENSE](./LICENSE) for full details.

---

## 👨‍💻 Credits

**Creator**: [Zelvior](https://github.com/zelvior) (Pakistan)  
**Version**: 6.0  
**Release Year**: 2025  
**License**: Apache 2.0  

### Technologies Used
| Technology | Purpose | Link |
|-----------|---------|------|
| **OpenRouter** | Model provider & API | https://openrouter.ai |
| **Tailwind CSS** | Utility-first styling | https://tailwindcss.com |
| **Marked.js** | Markdown parsing | https://marked.js.org |
| **Highlight.js** | Syntax highlighting | https://highlightjs.org |
| **DOMPurify** | XSS protection | https://github.com/cure53/DOMPurify |
| **Google Fonts** | Typography (Syne, Inter, JetBrains Mono) | https://fonts.google.com |

### Acknowledgments
- OpenRouter team for the excellent model API
- All open-source contributors
- Community feedback and suggestions
- Everyone who believes in privacy-first software

---

## 📝 Changelog

### v6.0 (Current)
- ✨ **Thinking Steps**: View AI reasoning process (Gemini-style)
- ✨ **Web Search**: Enable web search context for current information
- ✨ **Deep Thinking**: Toggle reasoning mode for capable models
- ✨ **Enhanced Canvas**: Improved code editor and preview
- ✨ **Achievements**: Unlock badges and earn XP
- ✨ **Cosmetics Store**: Purchase UI customizations
- 🎨 **Improved UI**: Refined dark theme with 8 color options
- 🔧 **Performance**: Optimized streaming and rendering
- 🐛 **Bug Fixes**: Various stability improvements

### v5.0
- ✨ Voice input via Web Speech API
- ✨ File attachments (RAG-Lite)
- ✨ Interactive code editor in canvas
- ✨ Download code blocks
- ✨ Conversation branching
- ✨ Separable system prompt + custom instructions

### v4.0
- ✨ Context window trimming
- ✨ Regenerate button
- ✨ Export chat as Markdown/JSON
- ✨ Scroll-to-bottom during generation
- ✨ Per-message actions (copy, regenerate)
- ✨ Color themes
- ✨ Auto-scroll toggle

### v3.0 & Earlier
- Core chat interface
- Model selection
- Real-time streaming
- Settings & customization

---

## 📞 Support

### Getting Help
1. Check the [GitHub Issues](https://github.com/zelvior/chatbot/issues)
2. Review this README's FAQ section
3. Create a new issue with:
   - Browser + version
   - Steps to reproduce
   - Expected vs. actual behavior
   - Screenshots if applicable

### Reporting Bugs
- Be specific and include steps to reproduce
- Include browser console errors (F12)
- Mention your OS and browser version
- Check if issue exists already

### Feature Requests
- Describe the feature clearly
- Explain the use case
- Suggest implementation if possible
- Check existing issues first

---

## 🎓 Learning Resources

### Documentation
- **OpenRouter Docs**: https://openrouter.ai/docs
- **Marked.js Docs**: https://marked.js.org
- **Highlight.js**: https://highlightjs.org
- **MDN Web Docs**: https://developer.mozilla.org
- **Tailwind CSS**: https://tailwindcss.com/docs

### Tutorials
- Web Speech API: https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API
- Server-Sent Events: https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events
- IndexedDB: https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API
- Fetch API: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

---

## ⚠️ Disclaimer

VortexAI is provided **"as is"** without warranty or guarantee of any kind.

**Users are responsible for:**
- ✋ Verifying all AI-generated content
- ✋ Complying with OpenRouter terms of service
- ✋ Safeguarding their API keys
- ✋ Legal use of the software

**The creators are not liable for:**
- ❌ Damages or data loss
- ❌ Misuse or misinterpretation of AI outputs
- ❌ Service interruptions
- ❌ Model provider changes or limitations

---

## 🎉 Fun Facts

- 🏗️ **Single HTML File**: Everything in one file—no build, no dependencies
- 🔒 **100% Client-Side**: Zero backend, zero servers, zero tracking
- ⚡ **Lightning Fast**: Instant load, instant response
- 🎨 **Fully Customizable**: 8 themes, 2 fonts, light/dark modes
- 🌍 **Works Offline**: Chat history and settings stored locally
- 📱 **Mobile First**: Designed and tested on all devices
- 🧠 **No AI Censoring**: Unfiltered access to 100+ models
- 🆓 **Completely Free**: No ads, no tracking, no limits

---

## 🚀 Get Started Now!

**👉 [Open VortexAI](https://zelvior.github.io/chatbot/)**

---

**Made with ❤️ by [Zelvior](https://github.com/zelvior) · Pakistan · 2025**

*Privacy-first. Open-source. Production-ready.*
