Once installed, Codex can run interactively simply by running the command 
	`$ codex`. Several flags exist when running codex, including

- -C {working_dir} - Swap the working directory
- -i {image1, image2} - Attach images as default context
- --search "prompt"  - enable live web search by default

# Essential Commands

## Model Options

- **/status**: Inspect the active session
- **/permissions**: Change the permissions behavior
- **/model**: Change the model of reasoning effort
- **/goal**: Set a goal for longer tasks
- **/plan**: plan before implementation of larger tasks
- **/mention**: Attach a file or folder to provide context

## Code Review and Git

- **/diff**: inspect git changes, including untracked files
	- You can ask a follow up to inspect the changes
- **/review**: Review the working tree or a PR

## Session Options

- **/compact**: Compress a long session to reduce the context window, and reduce token usage.
- **/new**: start a new chat
- **/resume**: Resume a previous saved chat
- **/fork**: Branch the chat into a new chat
- **/clear**: Clear the terminal and start a new chat
- **/rename**: Rename the current chat
- **/archive**: Archive the current chat
- **/delete**: Delete the current session (!warning: Permanent)
- **/exit**: Exit the environment

## Concurrent Agents

- **/side**: While a task is running, ask a question without disturbing the main task
	- Generally used for small explanations, or risk checks.
- **/ps**: Inpsect long-running commands in the background
- **/stop**: Stop long-running background commands

## Connections

- [[Codex CLI Handbook]]
- [[Codex Basics]]
