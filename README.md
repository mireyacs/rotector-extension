<h1 align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/png/rotector-logo-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="./assets/png/rotector-logo-light.png">
    <img width="300" alt="Rotector Extension" src="./assets/png/rotector-logo-light.png">
  </picture>
  <br>
  <a href="https://github.com/mireyacs/rotector-extension/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/mireyacs/rotector-extension?style=flat-square&color=4a92e1">
  </a>
  <a href="https://github.com/mireyacs/rotector-extension/issues">
    <img src="https://img.shields.io/github/issues/mireyacs/rotector-extension?style=flat-square&color=4a92e1">
  </a>
</h1>

<p align="center">
  <em>A browser extension that integrates with the <a href="https://github.com/robalyx/rotector">Rotector</a> system to help identify inappropriate users on Roblox.</em>
</p>

---

> [!WARNING]
> **This is a jailbroken/modified variant** of the original Rotector extension. This fork removes client identification tracking and other restrictive anti-abuse measures that may negatively impact legitimate users.

> [!IMPORTANT]
> This is a **community-driven initiative** and is not affiliated with, endorsed by, or sponsored by Roblox Corporation. This fork is not affiliated with the original developers (jaxron/robalyx) or their official releases.

---

## 🔓 What's Different in This Fork?

This is a **jailbroken variant** of the original Rotector extension, forked from [jaxron's repository](https://github.com/robalyx/rotector-extension). This version removes the client identification tracking system that was introduced as an "anti-abuse measure."

### 🚫 Removed: Client Identification Header

The original extension includes the user's client ID (Roblox user ID) with every API request via the `X-Client-ID` header. This fork removes that tracking mechanism entirely.

### ⚠️ Why This Matters: Problems with Client Identification

The implementation of client identification as an anti-abuse measure creates several significant issues for legitimate users:

#### 1. **False Positives and Unfair Bans**
- Legitimate users can be falsely flagged or banned based on automated systems that may misinterpret normal usage patterns
- Once a client ID is associated with a ban, users have no recourse if the ban was issued in error
- The system lacks proper appeal mechanisms for users who believe they were incorrectly flagged

#### 2. **Bias and Hypocrisy in Enforcement**
- The ban system appears to be inconsistently applied, with some users facing restrictions while others with similar behavior patterns remain unaffected
- There are concerns about selective enforcement based on community relationships rather than objective rule violations
- The developer's personal relationships within the community may influence who gets flagged and who doesn't

#### 3. **Privacy and Tracking Concerns**
- Forcing users to include their client ID with every request creates an unnecessary tracking mechanism
- This data can be used to build profiles of user behavior beyond what's necessary for the extension's core functionality
- Users who wish to use the extension anonymously or without being tracked are unable to do so

#### 4. **Disruption to Legitimate Use Cases**
- Users who have been incorrectly banned cannot use the extension even if they've done nothing wrong
- The system punishes users preemptively, potentially blocking access before any actual abuse occurs
- Legitimate users may be caught in automated filters that are overly aggressive

#### 5. **Ethical Concerns with Development Practices**
- The original developer (jaxron) has had furthermore interactions with Ruben Sim and the EASI project, as well as TASE (which is a close replica of EASI)
- There are documented concerns about Ruben Sim's past behavior and the appropriateness of such partnerships
- More critically, the developer is aware that Ruben Sim's developer for EASI is a minor, yet has exposed this minor to inappropriate content while developing systems meant to combat inappropriate users on Roblox
- The involvement with both EASI and TASE raises questions about the developer's judgment in choosing collaborative partners
- This creates a concerning contradiction where the system designed to protect children may itself involve inappropriate exposure of minors

### ✅ What This Fork Provides

- **No client identification tracking** - Your Roblox user ID is not sent with API requests
- **Privacy-focused** - Reduced data collection and tracking
- **Fair access** - Users who may have been incorrectly flagged can still use the extension
- **Transparency** - Open source modifications that you can verify yourself

## ❓ How It Works

This extension is a browser-based client for the [Rotector](https://github.com/robalyx/rotector) system. It communicates with Rotector's API service to display status indicators for Roblox users directly on the Roblox website.

The extension does not perform any analysis itself. All user analysis is performed by the Rotector system using AI and specialized algorithms. The extension simply displays the results of this analysis to help users identify potentially inappropriate accounts while browsing Roblox.

## 🌐 Learn More

Want to learn more about the Rotector project? Visit their website at **[rotector.com](https://rotector.com)** to explore the full system and see how their browser extension fits into the larger ecosystem of child safety tools.

<p align="center">
  <img src="./assets/png/website.png" alt="Rotector Website - Browser Extension Section" width="700">
</p>

<p align="center">
  <a href="https://chromewebstore.google.com/detail/rotector/ilegibonffbmecfchpcmcmknocboagan">
    <img src="https://img.shields.io/chrome-web-store/v/ilegibonffbmecfchpcmcmknocboagan?style=flat-square&color=4a92e1&label=chrome%20extension" alt="Chrome Web Store">
  </a>
  <a href="https://addons.mozilla.org/en-US/firefox/addon/rotector/">
    <img src="https://img.shields.io/amo/v/rotector?style=flat-square&color=4a92e1&label=firefox%20extension" alt="Firefox Add-ons">
  </a>
</p>

## 📦 Installation

### 🏪 From Browser Stores (Soon)

- **Chrome**: [Chrome Web Store](#)
- **Firefox**: [Firefox Add-ons](#)

### 🔧 From Source

#### Prerequisites

- [Bun](https://bun.sh/) (v1.2+)
- Node.js 18+

#### Setup

```bash
# Clone the repository
git clone https://github.com/mireyacs/rotector-extension.git
cd rotector-extension

# Install dependencies
bun install

# Development
bun run dev          # Chrome
bun run dev:firefox  # Firefox

# Build for production
bun run build         # Chrome
bun run build:firefox # Firefox

# Create distributable packages
bun run zip          # Chrome
bun run zip:firefox  # Firefox
```

#### 🔄 Loading the Extension

##### Chrome

1. Navigate to `chrome://extensions/`
2. Enable "Developer mode"
3. Click "Load unpacked"
4. Select the `.output/chrome-mv3` directory

##### Firefox

1. Navigate to `about:debugging`
2. Click "This Firefox"
3. Click "Load Temporary Add-on"
4. Select any file in the `.output/firefox-mv3` directory

## 📋 Usage

1. Install the extension in your browser
2. Navigate to any Roblox page (home/profile/friends/groups)
3. Look for safety indicators next to users:
   - 🟢 Safe users
   - 🟡 Flagged (needs review)
   - 🔴 Confirmed as inappropriate
4. Click on indicators for detailed information
5. Use the voting system to help improve accuracy
6. Access settings and statistics via the extension popup

### 🌐 Supported Pages

- **Home Page** (`/home`) - Analyzes users in the friends carousel
- **Profile Pages** (`/users/*/profile`) - Analyzes current user and friends
- **Friends Pages** (`/users/*/friends`, `/users/*/followers`, `/users/*/following`) - Bulk analysis of user lists
- **Groups Pages** (`/groups/*/members`) - Processes group member lists
- **Report Pages** (`/report`) - Automated form filling for flagged users

## 🛠️ Development

### 🔧 Tech Stack

#### Core Technologies

- **Framework**: [WXT](https://wxt.dev/) - Modern web extension framework
- **Frontend**: [Svelte 5](https://svelte.dev/) with runes syntax
- **Language**: [TypeScript](https://www.typescriptlang.org/) (100% type coverage with strict mode)
- **CSS**: [Tailwind CSS 4](https://tailwindcss.com/) with [PostCSS](https://postcss.org/)
- **Build Tool**: [Vite](https://vite.dev/) with [Lightning CSS](https://lightningcss.dev/) minification
- **Package Manager**: [Bun](https://bun.sh/) (v1.2+)

#### Development Tools

- **Code Quality**: [ESLint](https://eslint.org/) with TypeScript and Svelte plugins
- **Dead Code**: [Knip](https://knip.dev/) for analysis
- **Type Checking**: [svelte-check](https://www.npmjs.com/package/svelte-check) with TypeScript integration
- **Hot Reload**: Built-in with [WXT](https://wxt.dev/) development tools

### ✅ Quality Checks

```bash
# Run all quality checks
bun run quality

# Individual checks
bun run check        # Svelte type checking
bun run lint         # ESLint
bun run lint:fix     # ESLint + Auto-fix
bun run knip         # Dead code detection
```

### 📁 Project Structure

```
src/
├── assets/          # Static assets
├── components/      # Svelte 5 components
│   ├── features/    # Main feature components
│   ├── popup/       # Extension popup components
│   ├── status/      # Status indicators
│   └── ui/          # Reusable UI components
├── entrypoints/     # Extension entry points
│   └── popup/       # Popup interface
├── lib/             # Core logic
│   ├── controllers/ # Page-specific controllers
│   ├── services/    # API and external services
│   ├── stores/      # State management
│   ├── types/       # TypeScript definitions
│   └── utils/       # Utility functions
└── styles/          # Organized CSS modules
    ├── base/        # Foundation styles
    ├── components/  # Generic component styles
    ├── features/    # Feature-specific styles
    │   ├── changelog/
    │   ├── modal/
    │   ├── report-helper/
    │   ├── settings/
    │   ├── statistics/
    │   └── tooltip/
    └── theme/       # Design tokens
```

## 🤝 Contributing

Contributions are welcome! This fork aims to provide a more privacy-respecting and fair alternative to the original extension. Please:

1. Fork the repository
2. Create a feature branch
3. Run quality checks before committing
4. Submit a pull request

Please note that this project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md).

## 📝 Fork Information

This is a community fork of the original Rotector extension. The original repository can be found at [robalyx/rotector-extension](https://github.com/robalyx/rotector-extension) (maintained by jaxron).

### Key Modifications

- ✅ Removed `X-Client-ID` header from all API requests
- ✅ Removed client identification tracking
- ✅ Maintained full compatibility with Rotector API
- ✅ All other functionality remains unchanged

### Why Fork?

This fork was created to address concerns about:
- Privacy and unnecessary tracking
- Fair access for all users
- Transparency in anti-abuse measures
- Ethical development practices

## 💬 Support

- **Issues**: [GitHub Issues](https://github.com/mireyacs/rotector-extension/issues)
- **Discord**: Contact me on Discord: **azula.cs**

## 📄 License

This project is licensed under the GNU General Public License v2.0 - see the [LICENSE](LICENSE) file for details.

---

## ⚖️ Disclaimer

This fork is provided as-is for users who wish to use the Rotector extension without client identification tracking. The maintainers of this fork are not responsible for any issues that may arise from using this modified version, including but not limited to:

- API compatibility issues if the official Rotector service changes
- Any disputes with the original developers
- Service disruptions or rate limiting

Use at your own discretion. This fork is not endorsed by or affiliated with the original Rotector project or its developers.

---

Built with ❤️ for a safer and more privacy-respecting Roblox community
