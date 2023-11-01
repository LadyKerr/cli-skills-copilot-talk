---
theme: mokkapps
title: GitHub Copilot for CLI
favicon: ""
layout: cover
lineNumbers: true
---

# Take your command line skills to the next level with
# GitHub Copilot in the CLI 🚀

---
layout: about-me
---

---
layout: intro
image: 'https://github.com/community/community/assets/47188731/1ad0789f-3c29-446c-b071-7c721cd8734c'
---

# Agenda

- What is Github Copilot in the CLI?
- Installation, syntax and usage
- Live demos in the terminal
- Q&A

💡 This talk is **mostly demos** in the terminal to show you how to use GitHub Copilot for CLI.

---
layout: intro
---

# What is GitHub Copilot in the CLI?

GitHub Copilot for CLI provides a chat-like interface in the terminal that allows you to ask questions about the command line.

<!-- You can ask GitHub Copilot to provide either command suggestions or explanations of given commands. -->

<img src="https://github.com/community/community/assets/47188731/1ad0789f-3c29-446c-b071-7c721cd8734c" alt="ADD GIF OF CLI" width="600"/>

---
layout: intro
---

# Installation 🛠️
you must have an active GitHub Copilot subscription to use coplot for cli

- install GitHub CLI with your package manager
- authenticate in OAuth browser window
- install copilot cli extension

<br />

```bash
brew install gh
gh auth login
gh extension install github/gh-copilot
```

---
layout: intro
---

# How do you use it? 🤔

To begin, run the help command `gh copilot --help`:

```bash
gh copilot

Your AI command line copilot.

Usage:
copilot [command]

Available Commands:

explain Explain a command
suggest Suggest a command

Flags:

-h, --help help for copilot
-v, --version version for copilot

Use "copilot [command] --help" for more information about a command.

```

---
layout: intro
image: 'https://source.unsplash.com/collection/94734566/1920x1080'
---

# Copilot CLI Commands 🤖
there are two commands you can use with the gh copilot cli extension:

```bash
gh copilot explain
gh copilot suggest
```

---
layout: intro
image: 'https://source.unsplash.com/collection/94734566/1920x1080'
---

# Explain Command 🤖

this command is used to explain any shell, git or gh cli command:

```bash
gh copilot explain [what you want to know more about]
```

you can also run:

```bash
gh copilot explain
```

and follow the on screen prompts

---
layout: intro
image: 'https://source.unsplash.com/collection/94734566/1920x1080'
---

# Suggest Command 🤖

this command is used to get suggestions for any shell, git or gh cli inquiry:

```bash
gh copilot suggest [what you want to do]
```

you can also run:
```bash
gh copilot suggest
```

and follow the on screen prompts

---
layout: intro
class: "text-center"
---

# 💡 Tip: Create an alias

create your own alias for **gh copilot suggest/explain**

I'm using zsh so I ran:

```bash
echo 'alias ghs="gh copilot suggest"' >> ~/.zshrc 
&& echo 'alias ghe="gh copilot explain"' >> ~/.zshrc 
&& source ~/.zshrc
```

---
layout: full
class: "text-center"
---

# Prompting Copilot to get the right output 🤖

**Goal:** create a new react project <br/>
**Problem:** I don't remember how to do this <br/>
**Solution:** Ask Copilot CLI

```bash
gh copilot suggest create a new react project named techy-trends
```
<!-- live terminal example here -->

<!-- show this AFTER the terminal demo - figure out on slidev -->
communicating effectively with copilot cli is essential to your success

---
layout: full
class: "text-center"
---

# Push a local folder to a new GitHub repo 🗂️
We can create a GitHub repo with the cli 

```bash
gh copilot suggest push a local folder to a github repo
```

---
layout: full
class: "text-center"
---

# Explain a command ⚠️
We can ask copilot cli to explain commands we copied from the internet

```bash
gh copilot explain 'git lfs migrate import --everything --include="*.gz,*.png,*.jar"'
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
NEVER RUN THIS ONE YOUR MACHINE

---

# Explain a dangerous command ⚠️
We can ask copilot cli to explain commands we copied fron the internet

```bash
gh copilot explain chmod -r 777 /
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
NEVER RUN THIS ONE YOUR MACHINE

---
layout: full
class: "text-center"
---

# Remove a file from a commit msg and <br/> keep the original commit msg 🧐
ever commit a file you didn't mean to add?
<!-- 
TODO: 
create a new folder and initialize git: `mkdir demo && cd demo && git init`
create two new files: `touch demo.md && touch mistake.md`
commit both files: `git add . && git commit -m "initial commit"`

add content to both files:
echo "I like gh copilot cli" > demo.md
echo "I'm at gh universe '23!" > mistake.md

commit both files: `git add . && git commit -m "add content to both files"`

Now ask copilot to suggest how remove the file and keep the commit
Ask to explain commands
run commands
show changes in vscode or just run git log and git status

-->

```bash
gh copilot suggest remove <filename> from last commit keeping commit message`

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# Retract a commit that's already been pushed
subtitle

```bash
github copilot suggest retract an already pushed commit
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

<!-- 
So I can find the commit hash by running `git log` copy the hash and run

git revert <commit hash>
 -->
---
layout: section
---

# Top 10 Questions about using the terminal
10 most asked questions about using the terminal answered by _gh_ copilot cli

---
layout: full
class: "text-center"
---

#  ❓delete a git branch locally and remotely ❓

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓kill processes with open files that have been deleted ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ modify existing, unpushed commit messages ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ check if a directory exists in shell script ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ rename a local git branch ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ see hidden files in current directory ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ undo the most recent local git commit ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ make git forget about a file that was tracked, but is now in .gitignore ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ check if a directory exists in shell script ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ exit vim ❓
subtitle

```bash

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

---
layout: full
class: "text-center"
---

# ❓ give me a suggestion ❓
What would you like me to ask?

```bash
gh copilot suggest/explain ??
```
<!-- live terminal example here -->

---
layout: image-right
image: public reporepo
---

# ✨ Try it for yourself! ✨

Copilot for CLI is in public beta 

```bash
gh extension install github/gh-copilot
```
QR CODE

Add repo image link or discussion board for cli

---
layout: outro
---

# Thanks! ✨

SCAN FOR SLIDES:

QR CODE to repo with slides

[Add link for thhose who have slide]()
