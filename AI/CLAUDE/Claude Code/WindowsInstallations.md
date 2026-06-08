## Install Claude Code on Windows

### Option 1: PowerShell (Recommended)

1. Open **PowerShell** as a normal user.
2. Run the official installation command from Anthropic's documentation.

You can find the latest installation instructions here:

[Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code?utm_source=chatgpt.com)

3. After installation completes, restart PowerShell.

4. Verify the installation:

```powershell
claude --version
```

5. Navigate to your project folder and start Claude Code:

```powershell
cd path\to\your\project
claude
```

---

### Option 2: Command Prompt (CMD)

1. Open **Command Prompt**.
2. Run the official Windows installation command from the documentation.
3. Restart the terminal after installation.
4. Verify:

```cmd
claude --version
```

5. Start Claude Code:

```cmd
claude
```

---

### Option 3: Winget

If you use Windows Package Manager:

```powershell
winget install Anthropic.ClaudeCode
```

Then verify:

```powershell
claude --version
```

> Note: Winget installations may not support the same auto-update behavior as the official installer.

---

## First-Time Setup

When you run:

```powershell
claude
```

Claude Code will prompt you to:

* Choose a color theme
* Sign in with your account

  * Claude Pro
  * Claude Max
  * Claude Enterprise
* Or use an API key

After signing in, Claude Code is ready to use.

---

## Common Issues

### `claude` is not recognized

If you see:

```text
'claude' is not recognized as an internal or external command
```

Try:

* Closing and reopening PowerShell/CMD
* Restarting Windows Terminal
* Signing out and back in
* Reinstalling Claude Code

### Check Installation

Run:

```powershell
where.exe claude
```

This should show the location of the Claude executable.

---

### Test It

Create or open a project folder:

```powershell
cd C:\Projects\MyApp
claude
```

Then try prompts like:

* "Explain this codebase."
* "Find potential bugs."
* "Run the tests and summarize failures."
* "Refactor this function."

Claude Code will have access to that folder and its subfolders while you're working there.
