The codex CLI is a local coding agent ran from the terminal. It can perform various tasks on your computer, such as:

- Inspecting files
- Searching a repository
- Editing files
- Running shell commands and tests
- Inspecting git changes
- Reviewing code
- Process and review images
- Search the web
- Connect to external tools through MCP
- Run non-interactively from scripts
- Delegate independent work to subagents

The user prompts the model, and it gathers contexts, reasons, and requests a tool action, such as reading a file, or running tests. It then evaluates the result of the tool action, and decides the next tool action. 

# Codex's Five Controls
## Context
Context is the information that codex can use, such as your prompt, repository files, AGENTS.md, MCP / web search data, and more. You want to give **the smallest ammount of information sufficent for the task** as too much context can leak bad context, and bad context causes bad work. 

## Working Directory
The working directory tell Codex where the task starts. For example, we can run codex from a directory, and use that as the directory to work in
```bash
cd ~/code/my-project
codex
```

## Sandbox
The sandbox limits what model-generated shell commands can access. The mains modes are:

**Read-only** mode: Used for inspection, planning, and explaining
**workspace-write** mode(default): Used for normal implementation work
**danger-full-access** mode: Exceptional trusted environments.

Generally, you want to use the lowest permission set to complete the task.

## Approval Policy
The approval policy controls when codex asks to perform an action. In the CLI, there are three approval policies:

**Untrusted**: Prompts the user for confirmation of any command or action that is not pre-approved trusted. 
**on-request**: When an agent requires elevated actions or decides it needs explicit permission, ask.
**Never**: Disables interactive prompts entirely, every command runs straight through, though actions remain bound by your sandbox limitations. 

A safe, commonly used combination is 
```bash
codex --sandbox workspace-write --ask-for-approval on-request
```

## Model and reasoning effort
The model performs the reasoning and tool selection. The available models change, but at the time of writing (Aug 19, 2026) the best model is GPT5.6-Sol. The /model command can change the model, and its reasoning level. /status shows the active model and session configuration, to validate the session configuration. 

## Connections

- [[Codex CLI Handbook]]
- [[Operating the CLI]]
- [[Natural Language Processing - Aug 18]]
