

https://github.com/user-attachments/assets/9cc2c730-b521-40d5-83c5-4537eb3d55d0

# Git Reword

A fast, native bash script to rename or edit older git commit messages without manual interactive rebase. 
Features inline renaming, interactive text editor mode, and magic Zsh autocompletion with inline commit messages.

## Quick Install

Copy and paste this block into your terminal to install `git-reword` and its Zsh autocompletion instantly:

```bash
# 1. Install the script to your local bin
mkdir -p ~/.local/bin
curl -o ~/.local/bin/git-reword https://raw.githubusercontent.com/mazzoccantelorenzo/git-reword/main/git-reword
chmod +x ~/.local/bin/git-reword

# 2. Install Zsh autocompletion
mkdir -p ~/.zsh/completions
curl -o ~/.zsh/completions/_git-reword https://raw.githubusercontent.com/mazzoccantelorenzo/git-reword/main/_git-reword

# 3. Add to PATH (add to ~/.zshrc or ~/.bashrc)
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc

# 4. Enable Zsh autocompletion
# IMPORTANT: Open your ~/.zshrc and add this line BEFORE Oh-My-Zsh is loaded (or before compinit):
# fpath=(~/.zsh/completions $fpath)
```
*(After installing, run `source ~/.zshrc` or restart your terminal).*

## Usage

### 1. Magic Zsh Autocompletion
Type `git reword ` and press `TAB`. You will see a dropdown menu showing recent commit hashes and their titles!
Select an hash, add a space, and press `TAB` again. Zsh will fetch the old commit message and inject it into your terminal so you can edit it with your arrow keys!

### 2. Inline Mode (Instant Replace)
If you know exactly what the new message should be, pass it as the second argument. It will rewrite history instantly.
```bash
git reword <commit-hash> "Your brand new commit message"
```

### 3. Interactive Mode (Text Editor)
Omit the message. It will automatically trigger the rebase and drop you into your default text editor (Vim/Nano) pre-filled with the original message.
```bash
git reword <commit-hash>
```

## How it works
This script uses standard Git environment variables (`GIT_SEQUENCE_EDITOR` and `GIT_EDITOR`) to hijack the interactive rebase instruction sheet. It automatically replaces `pick` with `reword` for the target commit using `sed`, completely bypassing manual steps.

## License
MIT


## SEO Keywords (ignore)
*How to rename an old git commit message*
*Change an older commit message without interactive rebase*
*Git modify old commit fast*
*Git reword alias for zsh and bash*
*Fix typo in old git commit easily*
