# How Claude Code Works

Claude Code is different from typical chat applications. Understanding how it works under the hood will help you use it more effectively.

---

# The Agentic Loop

Claude Code is best explained through the **agentic loop**:

### Step 1: Enter a Prompt

* You enter a prompt into Claude Code.

### Step 2: Gather Context

* Claude gathers the context it needs.
* It interacts with the model to determine what information is required.
* The model may return text or a tool call that Claude Code can execute.

### Step 3: Take Action

* Claude performs actions based on your request.
* Examples include:

  * Editing files
  * Running terminal commands
  * Searching for information
  * Updating code across a project

### Step 4: Verify Results

* Claude checks the outcome of its actions.
* It determines whether the results satisfy the original request.

### Step 5: Repeat if Necessary

* If the goal is achieved, Claude finishes and waits for the next prompt.
* If the goal is not achieved, Claude loops back and continues working until the results are complete and verifiable.
* 
<img width="3840" height="2160" alt="image" src="https://github.com/user-attachments/assets/78bbf3e8-51a6-4801-b883-56801f4acc7a" />

### Human-in-the-Loop Control

Throughout the process, you can:

* Add additional context
* Interrupt execution
* Redirect the approach
* Clarify requirements

This allows you to guide the agent toward the desired outcome at any time.

---

# Context

Claude has a **context window**, which acts as its working memory.

The context window can contain:

* Conversation history
* File contents
* Command outputs
* Tool results
* Other relevant information

### What Happens When Context Fills Up?

When the context limit is reached:

* Claude Code automatically compacts the conversation.
* It determines what information can be:

  * Removed
  * Condensed
  * Summarized

This helps bring the context window back to a usable size while preserving important information.

---

# Tools

Tools are the backbone of how AI agents work.

### Traditional AI Assistants

Most AI assistants:

* Receive text input
* Return text output

### Claude Code

Claude Code can go beyond text by using tools to take action.

Examples include:

* File reading tools
* File editing tools
* Terminal command execution
* Web search capabilities
* Project analysis tools

### How Tool Usage Works

Claude Code uses semantic understanding to determine:

* When a tool should be used
* Which tool is appropriate
* How to interpret the tool's output
* What action should be taken next

This enables Claude Code to actively work toward completing a task rather than simply describing how to do it.

---

# Permissions

Claude Code includes multiple permission modes that control what actions it can perform.

## Default Behavior

Claude asks for explicit permission before:

* Editing files
* Running shell commands

This provides maximum oversight and control.

## Auto-Accept Mode

In this mode:

* File edits are performed without asking.
* Shell commands still require approval.

This can speed up workflows while maintaining safeguards around command execution.

## Plan Mode

Plan Mode uses read-only tools to:

* Inspect the codebase
* Analyze the task
* Create a plan of action

No changes are made until you decide to proceed.

### Important Consideration

All permission settings can be configured in your settings file.

Be cautious when reducing permissions:

* Mistakes can happen.
* Automated actions may be harder to review beforehand.
* Running commands without oversight increases risk.

Maintaining appropriate safeguards helps prevent unintended changes.

---

# Recap

### Key Components of Claude Code

Claude Code combines several agentic concepts:

* Agentic Loop
* Managed Context Window
* Tool Usage
* Configurable Permissions

### What This Enables

Claude Code can:

* Read and understand your codebase
* Gather relevant context
* Take actions on your behalf
* Verify its own results
* Iterate until a task is completed

All of this happens directly inside your terminal.

That combination of reasoning, action, verification, and tool usage is what makes Claude Code fundamentally different from a traditional chat interface.
