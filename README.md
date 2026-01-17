# Custom Unix Shell

## Project Overview
This project involves building a fully functional command-line interpreter (Shell) similar to `bash` or `zsh`. It delves deep into the Linux kernel's process management, handling the lifecycle of processes via the `fork-exec-wait` model. The shell supports professional features like I/O redirection, piping, background job control, and scripting capabilities.

## Key Features

### 1. Process Management
- **Core Cycle:** Implemented the fundamental `fork()`, `execvp()`, and `waitpid()` cycle to execute external commands.
- **Background Execution (`&`):** capability to run jobs in the background and properly reap "zombie" processes using non-blocking waits.

### 2. I/O Redirection & Pipes
- **Redirection:** Implemented input (`<`) and output (`>`) redirection using `dup2()` and file descriptor manipulation.
- **Pipes (`|`):** Enabled inter-process communication by chaining commands (e.g., `ls | grep .c`) using `pipe()`.

### 3. Built-in Commands
- **Internal Logic:** Implemented shell-resident commands like `cd` (using `chdir`), `exit`, and `help`.
- **History:** Maintains a history of the last 20 commands, accessible via the `history` command or `!n` expansion.

### 4. Scripting & Variables
- **Control Structures:** Added support for `if-then-else-fi` conditional logic based on process exit status.
- **Variables:** Implemented local shell variables (`VAR=value`) and expansion (`$VAR`).

### 5. Professional Integration
- **GNU Readline:** Linked against the `readline` library to provide tab completion and arrow-key history navigation.

## Technologies Used
- **Language:** C
- **System Calls:** `fork`, `exec`, `wait`, `pipe`, `dup2`, `open`, `close`
- **Libraries:** GNU Readline
- **Build Tool:** GNU Make
