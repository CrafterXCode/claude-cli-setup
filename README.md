# Claude CLI Setup Guide

[![GitHub](https://img.shields.io/badge/GitHub-CrafterXCode-blue)](https://github.com/CrafterXCode/claude-cli-setup)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Platform Support](https://img.shields.io/badge/Platform-macOS%20%7C%20Ubuntu%20%7C%20Windows-brightgreen)](README.md)

**Complete setup and installation guide for Claude AI CLI with VS Code integration across Windows, macOS, and Ubuntu Linux systems.**

This repository provides step-by-step instructions to configure Claude AI (powered by Anthropic) on your development machine, enabling seamless integration with Visual Studio Code and command-line interfaces.

---

## Table of Contents

- [Overview](#overview)
- [Quick Start](#quick-start)
- [Platform-Specific Guides](#platform-specific-guides)
- [Prerequisites](#prerequisites)
- [Installation Methods](#installation-methods)
- [API Key Configuration](#api-key-configuration)
- [Security Best Practices](#security-best-practices)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [Support](#support)

---

## Overview

Claude is an advanced AI assistant developed by Anthropic. This setup repository helps developers integrate Claude into their development workflow with VS Code, enabling AI-powered code assistance, debugging, and development tasks.

### Why Use Claude CLI?

- **Enhanced Productivity**: Get AI-powered code suggestions and completions
- **Advanced Code Analysis**: Receive intelligent debugging and code review assistance
- **Natural Language Integration**: Interact with AI through natural language commands
- **Cross-Platform Support**: Works on Windows, macOS, and Linux systems
- **Secure API Integration**: Direct integration with Anthropic's Claude API

---

## Quick Start

### For macOS:
```bash
# Clone the repository
git clone https://github.com/CrafterXCode/claude-cli-setup.git
cd claude-cli-setup

# Follow macOS setup guide
cat macOS-Claude-Setup.md
```

### For Ubuntu/Linux:
```bash
# Clone the repository
git clone https://github.com/CrafterXCode/claude-cli-setup.git
cd claude-cli-setup

# Follow Ubuntu setup guide
cat Ubuntu-Claude-Setup.md
```

### For Windows:
```powershell
# Clone the repository
git clone https://github.com/CrafterXCode/claude-cli-setup.git
cd claude-cli-setup

# Follow Windows setup guide
type Windows-Claude-Setup.md
```

---

## Platform-Specific Guides

Choose the guide that matches your operating system:

### 🍎 **macOS Setup**
Comprehensive guide for macOS 10.13+ systems including Homebrew installation and shell configuration.

→ [Read macOS Setup Guide](macOS-Claude-Setup.md)

**Includes:**
- Node.js installation via Homebrew
- Shell configuration (.bashrc/.zshrc)
- API key setup
- VS Code extension installation

### 🐧 **Ubuntu/Linux Setup**
Complete setup instructions for Ubuntu and other Linux distributions.

→ [Read Ubuntu Setup Guide](Ubuntu-Claude-Setup.md)

**Includes:**
- Package manager installation
- Environment variable configuration
- VS Code integration
- Terminal setup

### 🪟 **Windows Setup**
Full guidance for Windows 10+ systems with both PowerShell and Command Prompt options.

→ [Read Windows Setup Guide](Windows-Claude-Setup.md)

**Includes:**
- PowerShell script setup
- Batch file alternatives
- Environment variable persistence
- System integration

---

## Prerequisites

Before setting up Claude CLI, ensure you have:

### Required Software

| Component | Requirement | Download |
|-----------|-------------|----------|
| **Node.js** | Version 14+ | [nodejs.org](https://nodejs.org/) |
| **npm** | Included with Node.js | Bundled |
| **VS Code** | Latest version | [code.visualstudio.com](https://code.visualstudio.com/) |
| **Git** | Latest version | [git-scm.com](https://git-scm.com/) |

### System Requirements

- **RAM**: 4GB minimum (8GB recommended)
- **Disk Space**: 500MB free
- **Internet**: Required for API calls
- **OS Support**:
  - macOS 10.13 or later
  - Ubuntu 18.04 or later
  - Windows 10 or later

---

## Installation Methods

### Method 1: Automated Setup Script

The fastest way to get started:

```bash
# macOS/Linux
chmod +x setup-claude.sh
./setup-claude.sh
```

```powershell
# Windows (PowerShell)
./setup-claude.ps1
```

### Method 2: Manual Configuration

Follow the step-by-step instructions in your platform-specific guide:

1. Install Node.js and npm
2. Install VS Code
3. Obtain Anthropic API key
4. Configure environment variables
5. Install Claude extension

### Method 3: Docker Setup (Optional)

For containerized environments:

```bash
docker run -e ANTHROPIC_API_KEY=your-key node:18 /bin/bash
```

---

## API Key Configuration

### Getting Your API Key

1. Visit [Anthropic Console](https://console.anthropic.com/)
2. Sign in or create an account
3. Navigate to API Keys section
4. Click "Create Key"
5. Copy your API key securely

### Setting the API Key

**macOS/Linux:**
```bash
export ANTHROPIC_API_KEY="your-api-key-here"

# For persistence, add to ~/.bashrc or ~/.zshrc
echo 'export ANTHROPIC_API_KEY="your-api-key-here"' >> ~/.bashrc
source ~/.bashrc
```

**Windows (PowerShell):**
```powershell
$env:ANTHROPIC_API_KEY = "your-api-key-here"

# For persistence, add to profile
Add-Content -Path $PROFILE -Value "`$env:ANTHROPIC_API_KEY = 'your-api-key-here'"
. $PROFILE
```

**Windows (Command Prompt):**
```batch
setx ANTHROPIC_API_KEY "your-api-key-here"
```

---

## Security Best Practices

### ⚠️ Critical Security Guidelines

1. **Never Commit API Keys**
   ```bash
   # Add to .gitignore
   echo "*.env" >> .gitignore
   echo ".env.local" >> .gitignore
   ```

2. **Use Environment Variables**
   - Never hardcode API keys in your code
   - Always store in environment variables
   - Use `.env` files locally (don't commit them)

3. **Rotate Keys Regularly**
   - Change API keys every 90 days
   - Immediately rotate if compromised
   - Use the Anthropic Console to manage keys

4. **Restrict Key Permissions**
   - Use separate keys for development and production
   - Set rate limits if available
   - Monitor API usage in console

5. **Secure Your Shell Configuration**
   ```bash
   # Limit file permissions
   chmod 600 ~/.bashrc
   chmod 600 ~/.zshrc
   ```

---

## Troubleshooting

### Common Issues and Solutions

#### API Key Not Recognized
```bash
# Verify the key is set correctly
echo $ANTHROPIC_API_KEY

# Re-source your shell configuration
source ~/.bashrc  # macOS/Linux
. $PROFILE        # Windows PowerShell
```

#### Node.js Not Found
```bash
# macOS - Install via Homebrew
brew install node

# Ubuntu/Linux
sudo apt-get update
sudo apt-get install nodejs npm

# Verify installation
node --version
npm --version
```

#### VS Code Extension Not Appearing
- Restart VS Code completely
- Check Extensions marketplace for "Claude"
- Ensure you're using the official Claude extension
- Clear VS Code cache if needed

#### Permission Denied on Script Execution
```bash
# macOS/Linux - Make script executable
chmod +x setup-claude.sh
./setup-claude.sh
```

#### Invalid Character in API Key
- Verify you copied the entire key
- Check for extra spaces or quotes
- Don't modify the key format
- Download from Anthropic Console again if uncertain

---

## Features & Benefits

✅ **Cross-Platform Support** - Works on Windows, macOS, and Linux  
✅ **Easy Installation** - Automated scripts for quick setup  
✅ **Secure API Integration** - Industry-standard security practices  
✅ **VS Code Integration** - Seamless editor integration  
✅ **Full Documentation** - Comprehensive guides for all platforms  
✅ **Community Support** - Active maintenance and issue resolution  

---

## File Structure

```
claude-cli-setup/
├── README.md                      # This file
├── macOS-Claude-Setup.md          # macOS setup guide
├── Ubuntu-Claude-Setup.md         # Ubuntu/Linux setup guide
├── Windows-Claude-Setup.md        # Windows setup guide
├── setup-claude.sh               # Automated setup script (macOS/Linux)
└── setup-claude.ps1              # PowerShell setup script (Windows)
```

---

## System Requirements Details

### macOS
- **OS Version**: 10.13+
- **Terminal**: Bash, Zsh, or Fish
- **Package Manager**: Homebrew (optional but recommended)

### Ubuntu/Linux
- **Distributions**: Ubuntu 18.04 LTS or later, Debian, Fedora
- **Package Manager**: apt, yum, or dnf
- **Shells**: Bash, Zsh, Fish

### Windows
- **OS Version**: Windows 10 (Build 19041+) or Windows 11
- **Shells**: PowerShell or Command Prompt (cmd.exe)
- **VS Code**: Latest version recommended

---

## Configuration Files

### Environment Configuration

After setup, verify your configuration:

```bash
# Check API key is set
printenv | grep ANTHROPIC_API_KEY

# Verify Node.js
node --version

# Verify npm
npm --version

# Verify VS Code
code --version
```

---

## Support & Resources

### Documentation
- [Anthropic Official Docs](https://docs.anthropic.com/)
- [Claude API Reference](https://docs.anthropic.com/claude/reference)
- [VS Code Documentation](https://code.visualstudio.com/docs)

### Reporting Issues
- Check existing [GitHub Issues](https://github.com/CrafterXCode/claude-cli-setup/issues)
- Create a new issue with clear reproduction steps
- Include OS, Node.js, and npm versions

### Getting Help
- Review platform-specific guides
- Check troubleshooting section
- Search documentation
- Contact Anthropic support for API-related issues

---

## Contributing

Contributions are welcome! We appreciate help improving this guide.

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit clearly (`git commit -m 'Add improvement'`)
5. Push to the branch (`git push origin feature/improvement`)
6. Open a Pull Request

### Contribution Guidelines
- Test all changes on your platform
- Update documentation if needed
- Follow markdown formatting standards
- Include clear commit messages

---

## License

This project is licensed under the MIT License. See LICENSE file for details.

---

## Changelog

### v1.0.0 (Latest)
- Initial release with support for Windows, macOS, and Ubuntu
- Comprehensive setup guides for all platforms
- API key configuration documentation
- Security best practices
- Troubleshooting section

---

## Related Projects

- [Claude Documentation](https://docs.anthropic.com/)
- [Anthropic GitHub](https://github.com/anthropics)
- [VS Code Extensions](https://marketplace.visualstudio.com/)

---

## FAQ

**Q: Do I need a paid Anthropic account?**  
A: Check [Anthropic's pricing page](https://www.anthropic.com/pricing) for current plans and free tier options.

**Q: Can I use Claude offline?**  
A: No, Claude API requires an active internet connection.

**Q: Is my API key secure?**  
A: Yes, if you follow our security best practices. Never share your key publicly.

**Q: Which Claude model should I use?**  
A: Check the Anthropic documentation for the latest available models and their use cases.

---

## Contact & Social

- **GitHub**: [CrafterXCode](https://github.com/CrafterXCode/claude-cli-setup)
- **Issues**: [Report Issues Here](https://github.com/CrafterXCode/claude-cli-setup/issues)

---

## Disclaimer

This is an unofficial setup guide. Please refer to [Anthropic's official documentation](https://docs.anthropic.com/) for authoritative information about Claude and its APIs.

---

**Last Updated**: April 2026  
**Maintained By**: CrafterXCode Community
