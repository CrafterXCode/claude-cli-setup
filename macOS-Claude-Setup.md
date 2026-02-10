# macOS Claude Setup Guide

This guide provides instructions for setting up Claude Code on macOS with VS Code using an API key.

## Prerequisites

- macOS 10.13 or later
- Node.js and npm installed ([Download from nodejs.org](https://nodejs.org/) or use Homebrew)
- VS Code installed ([Download from code.visualstudio.com](https://code.visualstudio.com/))
- Terminal or preferred shell (Bash, Zsh, etc.)

## Installing Node.js (if not already installed)

### Using Homebrew (Recommended):

```bash
# Install Homebrew if you don't have it
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Node.js
brew install node
```

### Verify Installation:

```bash
node --version
npm --version
```

## Creating the Setup Script

Create a file called `setup-claude.sh`:

```bash
#!/bin/bash

# Set your API key (replace with your actual key)
export ANTHROPIC_API_KEY=your-api-key-here

# Determine the shell configuration file
if [[ "$SHELL" == *"zsh"* ]]; then
    SHELL_RC=~/.zshrc
else
    SHELL_RC=~/.bashrc
fi

# Add the API key to the shell configuration file
echo 'export ANTHROPIC_API_KEY=your-api-key-here' >> "$SHELL_RC"

# Apply changes
source "$SHELL_RC"

echo "Claude Code setup complete!"
echo "Please restart your terminal or run 'source $SHELL_RC' to apply changes"
```

## Installation Steps

1. Save the script as `setup-claude.sh` in your desired directory:
   ```bash
   touch setup-claude.sh
   ```

2. Replace `your-api-key-here` with your actual Anthropic API key in the script

3. Make the script executable:
   ```bash
   chmod +x setup-claude.sh
   ```

4. Run the setup script:
   ```bash
   ./setup-claude.sh
   ```

5. Restart your terminal or run:
   ```bash
   # For Zsh (default in macOS 10.15+)
   source ~/.zshrc
   
   # Or for Bash
   source ~/.bashrc
   ```

6. Open VS Code and install the Claude extension from the Extensions marketplace

## Verifying the Installation

To verify your API key is set correctly, run:

```bash
echo $ANTHROPIC_API_KEY
```

You should see your API key displayed in the terminal.

## Alternative: Using a .env File

If you prefer to keep your API key in a separate file:

1. Create a `.env` file in your project directory:
   ```bash
   echo "export ANTHROPIC_API_KEY=your-api-key-here" > .env
   ```

2. Source it before using Claude:
   ```bash
   source .env
   ```

3. **Important:** Add `.env` to your `.gitignore` to prevent committing sensitive information:
   ```bash
   echo ".env" >> .gitignore
   ```

## Using with Different Shells

### Zsh (Default in macOS 10.15+):
Edit `~/.zshrc` and add:
```bash
export ANTHROPIC_API_KEY=your-api-key-here
```

### Bash:
Edit `~/.bashrc` and add:
```bash
export ANTHROPIC_API_KEY=your-api-key-here
```

### Fish:
Edit `~/.config/fish/config.fish` and add:
```fish
set -gx ANTHROPIC_API_KEY your-api-key-here
```

Then reload with:
```bash
source ~/.config/fish/config.fish
```

## Uninstalling

To remove the Claude setup:

1. Remove the API key from your shell configuration:
   ```bash
   # For Zsh
   nano ~/.zshrc
   # Remove the line: export ANTHROPIC_API_KEY=...
   
   # For Bash
   nano ~/.bashrc
   # Remove the line: export ANTHROPIC_API_KEY=...
   ```

2. Save and close the editor

3. Restart your terminal

## Notes

- Your API key should be kept private and never shared or committed to version control
- You can generate an API key from the [Anthropic dashboard](https://console.anthropic.com/)
- macOS uses Zsh by default since version 10.15 (Catalina). Check your shell with `echo $SHELL`
- The setup script automatically detects whether you're using Bash or Zsh
- Homebrew is the recommended way to manage packages on macOS
- VS Code can be opened from the terminal with `code .` after installation

## Troubleshooting

**Issue:** "Command not found: setup-claude.sh"
- **Solution:** Make sure the script has execute permissions: `chmod +x setup-claude.sh`

**Issue:** API key not recognized
- **Solution:** Run `echo $ANTHROPIC_API_KEY` to verify the key is set. If not, either:
  - The script didn't run successfully, or
  - Your terminal session needs to be restarted

**Issue:** "Permission denied" when running the script
- **Solution:** Ensure the script is executable: `chmod +x setup-claude.sh`

**Issue:** Claude extension not appearing in VS Code
- **Solution:** Make sure:
  - VS Code is restarted after setting the API key
  - You're installing the correct Claude extension from the marketplace
  - Your macOS version is compatible with VS Code

**Issue:** Changes to shell configuration not taking effect
- **Solution:** Restart your terminal session or manually source your configuration file:
  ```bash
  source ~/.zshrc  # for Zsh
  # or
  source ~/.bashrc  # for Bash
  ```
