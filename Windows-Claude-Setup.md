# Windows Claude Setup Guide

This guide provides instructions for setting up Claude Code on Windows with VS Code using an API key.

## Prerequisites

- Windows 10 or later
- Node.js and npm installed ([Download from nodejs.org](https://nodejs.org/))
- VS Code installed ([Download from code.visualstudio.com](https://code.visualstudio.com/))
- PowerShell or Command Prompt

## Creating the Setup Script

Create a file called `setup-claude.ps1` (for PowerShell) or `setup-claude.bat` (for Command Prompt):

### Option 1: PowerShell Script

Create `setup-claude.ps1`:

```powershell
# Set your API key (replace with your actual key)
$env:ANTHROPIC_API_KEY = "your-api-key-here"

# Add to PowerShell profile for persistence
$profilePath = $PROFILE
if (-not (Test-Path $profilePath)) {
    New-Item -ItemType File -Path $profilePath -Force
}

Add-Content -Path $profilePath -Value "`n`$env:ANTHROPIC_API_KEY = 'your-api-key-here'"

Write-Host "Claude Code is ready to use!"
Write-Host "Please restart PowerShell or run: . `$PROFILE"
```

### Option 2: Command Prompt Batch Script

Create `setup-claude.bat`:

```batch
@echo off
REM Set your API key (replace with your actual key)
setx ANTHROPIC_API_KEY "your-api-key-here"

echo Claude Code environment variable has been set!
echo Please restart Command Prompt or close and reopen it for changes to take effect.
pause
```

## Installation Steps

### For PowerShell:

1. Save the script as `setup-claude.ps1` in your desired directory
2. Replace `your-api-key-here` with your actual Anthropic API key
3. Open PowerShell as Administrator
4. Run the following command:
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   .\setup-claude.ps1
   ```
5. Restart PowerShell or run `. $PROFILE`
6. Open VS Code and install the Claude extension from the Extensions marketplace

### For Command Prompt:

1. Save the script as `setup-claude.bat` in your desired directory
2. Replace `your-api-key-here` with your actual Anthropic API key
3. Right-click the batch file and select "Run as administrator"
4. Close and reopen Command Prompt for changes to take effect
5. Open VS Code and install the Claude extension from the Extensions marketplace

## Verifying the Installation

To verify your API key is set correctly, open PowerShell or Command Prompt and run:

```powershell
# PowerShell
echo $env:ANTHROPIC_API_KEY
```

or

```batch
REM Command Prompt
echo %ANTHROPIC_API_KEY%
```

## Notes

- Your API key should be kept private and never shared or committed to version control
- You can generate an API key from the [Anthropic dashboard](https://console.anthropic.com/)
- For PowerShell, you may need to adjust execution policies. See `Set-ExecutionPolicy` documentation
- Environment variables set with `setx` in Command Prompt are permanent and system-wide
- Environment variables set in PowerShell profiles are user-specific
- If using Windows Terminal, the setup works for both PowerShell and Command Prompt profiles

## Troubleshooting

**Issue:** "Cannot be loaded because running scripts is disabled"
- **Solution:** Run `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` in PowerShell as Administrator

**Issue:** API key not recognized
- **Solution:** Ensure the environment variable is set correctly by running the verification command above

**Issue:** Claude extension not appearing in VS Code
- **Solution:** Make sure VS Code is restarted after setting the API key, and check that you're installing the correct extension from the marketplace
