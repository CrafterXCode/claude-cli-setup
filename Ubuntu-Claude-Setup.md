# Ubuntu Claude Setup Guide

This guide provides instructions for setting up Claude Code on Ubuntu with VS Code using an API key.

## Creating the Setup Script

Create a file called `setup-claude.sh`:

```bash
#!/bin/bash

# Set your API key (replace with your actual key)
export ANTHROPIC_API_KEY=your-api-key-here

# Append to bashrc for persistence
echo 'export ANTHROPIC_API_KEY=your-api-key-here' >> ~/.bashrc

# Apply changes
source ~/.bashrc

echo "Claude Code is ready to use! Restart your terminal or run 'source ~/.bashrc'"
```

## Installation Steps

1. Save this file as `setup-claude.sh`
2. Replace `your-api-key-here` with your actual Anthropic API key
3. Run the following commands:
   ```bash
   chmod +x setup-claude.sh
   ./setup-claude.sh
   ```
4. Open VS Code and install the Claude extension from the Extensions marketplace

## Notes

- Ensure you have Node.js and npm installed on your system
- Your API key should be kept private and never committed to version control
- You can generate an API key from the Anthropic dashboard
