Here's a setup file for Claude Code on Ubuntu with VS Code using an API key:

Create a file called setup-claude.sh:

#!/bin/bash

# Install Claude Code CLI
curl -fsSL https://claude.ai/install.sh | bash

# Set your API key (replace with your actual key)
echo 'export ANTHROPIC_API_KEY=your-api-key-here' >> ~/.bashrc

# Apply changes
source ~/.bashrc

echo "Claude Code installed! Restart your terminal or run 'source ~/.bashrc'"
To use:

Save this file as setup-claude.sh
Replace your-api-key-here with your actual API key
Run: chmod +x setup-claude.sh && ./setup-claude.sh
Open VS Code and install the "Claude Code" extension from the Extensions marketplace
