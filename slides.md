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
layout: image-right
image: 'https://github.com/community/community/assets/47188731/1ad0789f-3c29-446c-b071-7c721cd8734c'
---

# What we'll cover:

- What is Github Copilot in the CLI?
- How to install and use it? 🤔
- My Hot Tip 💡 for using Copilot in the CLI 
- Lots and lots of live demos 💃🏼
- Give me a suggestion! 👀
- Q&A + Wrapup ❓

<!--
This talk is mostly demos in the terminal to show you how to use GitHub Copilot in the CLI. 
-->

---
layout: intro
---

# What is Copilot in the CLI?

GitHub Copilot in the CLI provides a chat-like interface in the terminal that allows you to ask questions about the command line.

<img src="https://github.com/LadyKerr/cli-skills-copilot/assets/47188731/ef7a4fca-72bf-41aa-a2b1-4617b31abbe7" alt="github copilot in the cli" width="600" />

<!--
You can ask GitHub Copilot to provide either command suggestions or explanations of given commands.

hink of it like copilot chat in your terminal, there to helo you with commands specific with working in the cli.
It is only here to answer questions related to using git, the github cli or answer general shell command questions.

If you ask it a programming question, it is not scoped to respond to those - copilot in the cli is here to helop you wuth your terminal needs. 

-->

---
layout: intro
---

# What does it do?

GitHub Copilot in the CLi is designed to answer questions about:
- general shell commands
- git commands
- _gh_ cli commands

<br />

<img src="https://github.com/LadyKerr/cli-skills-copilot/assets/47188731/e9546211-7370-4e1d-9090-1175ec55379b" alt="github copilot in the cli" width="600" />

---
layout: intro
---

# Getting Started: Installation 🛠️
💡 `You must have an active copilot subscription`

❶ install GitHub CLI with your package manager <br/>
❷ authenticate in OAuth browser window <br/>
❸ install gh-copilot cli extension

<br />

```bash
brew install gh
gh auth login
gh extension install github/gh-copilot
```

<!--
to install copilot in the cli, you must first install the gh cli using your preferred package manager. Since I have mac, I use homebrew so I ran brew install gh.

Once that's done, you can authenticate yourself and then install the extension by running gh extension install github/gh-copilot

Once that's done, the next thing I want you to do is to create an alias and this brings me to my hot tip of the day

-->
---
layout: intro
---

# 💡 Tip: Create an alias

create your own alias for **gh copilot suggest** && **gh copilot explain**

I'm using zsh so I ran:

```bash
alias copilot='gh copilot' ; echo 'alias copilot="gh copilot"' >> ~/.zshrc && source ~/.zshrc
alias gcs='gh copilot suggest' ; echo 'alias gcs="gh copilot suggest"' >> ~/.zshrc && source ~/.zshrc
alias gce='gh copilot explain' ; echo "alias gce='gh copilot explain'" >> ~/.zshrc && source ~/.zshrc
```
<!-- 
Create an alias! This will make interfacing with the cli a lot smoother because it saves you some keystrokes and you can get help faster.

Since Im using zsh, I ran the following commands for gh copilot, gh copilot suggest and gh copilot explain.

But speaking of aliases, what are the commands that we can to interact with copilot in the cli?
Let's keep going -->


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
  config      Configure options
  explain     Explain a command
  suggest     Suggest a command

Flags:
  -h, --help      help for copilot
  -v, --version   version for copilot

Use "copilot [command] --help" for more information about a command.

```
<!--
To get started, I recommend running the help command, gh copilot --help this is the response you will get you'll see a list of available commands, flags and info on how to get with specific commands. 

Let's take a further look at the available commands
-->

---
layout: intro
---

# Copilot CLI Commands 🤖
there are three commands you can use with the _gh_ copilot cli extension:

```bash
gh copilot explain
gh copilot suggest
gh copilot config
```

<!--
Now remember, I have aliases configured so if you see me running copilot, gcs or gce, know that Im using aliases that I created to use less keystrokes.

Ok let's take a closer look at the explain command
-->

---
layout: intro
image: 'https://source.unsplash.com/collection/94734566/1920x1080'
---

# Explain Command 🤖

this command is used to explain any shell, git or gh cli command:

```bash
gh copilot explain 'your query command in a string'

Example: gh copilot explain 'git lfs migrate import --everything --include="*.gz,*.png,*.jar"'
```

Yoiu can also follow the on screen prompts if you run this command:

```bash
gh copilot explain
```

<br />
💡 the command you want to be explained must be in a string

<!--
Let's ask copilot to explain cd ~

-->

---
layout: intro
---

# Suggest Command 🤖

this command is used to get suggestions for any shell, git or gh cli inquiry:

```bash
gh copilot suggest 'what you want to do' -t <git|gh|shell>

Example: gh copilot suggest 'install and configure git lfs'
```

you can also run:
```bash
gh copilot suggest
```

and follow the on screen prompts

---
layout: intro
---

# Config Command 🤖

this command gives you the option to opt in or out of usage analytics

```bash
gh copilot config
```

---
layout: intro
---

# Why do we need usage stats? 🧐

Copilot in the CLI sends a payload to our analytics system.

```bash
{
	"platform": "darwin",
	"architecture": "arm64",
	"version": "0.3.0-beta",
	"custom_event": "true",
	"event_parent_command": "explain",
	"event_name": "Explain",
	"sha": "089a53215fc4383179869f7f6132ce9d6e58754a",
	"thread_id": "e61d0d08-f6ba-465b-81cf-c30fd9127d70"
}
```

**You can opt out by using the `gh copilot config` command**

<!--
Now what do we do with this data?
Well, it helps us to identify whether you're actually finding copilot in the cli useful. 

For example, when we release a new version and see a spike in exceptions and response ratings, we want to understand if there is a regression or a platform nuance causing problems.

Privacy is our priority so we're not looking at the data of speficic users, but rather an aggregate of the data trends to inform our decisions.

-->

---
layout: image-left
image: https://media.giphy.com/media/5q3NyUvgt1w9unrLJ9/giphy.gif
---

## ok that was a lot of talking...

let's get into some demos 💃🏼

<img src="https://media.giphy.com/media/5q3NyUvgt1w9unrLJ9/giphy.gif" alt-="neicy nash saying time is ticking" />

---
layout: full
class: "text-center"
---

# Prompting Copilot to get the right output 🤖

**Goal:** create a new react project <br/>
**Problem:** I don't remember how to do this <br/>
**Solution:** Ask Copilot CLI

```bash
gh copilot suggest 'create a new react project named techy-trends'
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
gh copilot suggest 'push a local folder to a github repo'
```

---
layout: full
class: "text-center"
---

# Explain a command 🧐
We can ask copilot cli to explain commands we copied from the internet

```bash
gh copilot explain 'git lfs migrate import --everything --include="*.gz,*.png,*.jar"'
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->

---

# Explain a dangerous command ⚠️
We can ask copilot cli to explain commands that appears simple enough, but are actually dangerous

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

```bash
gh copilot suggest 'remove <filename> from last commit keeping commit message'

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

<!--  
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
---
layout: full
class: "text-center"
---

# Retract a commit that's already been pushed
subtitle

```bash
github copilot suggest 'retract an already pushed commit'
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
text if any to show

<!-- 
So I can find the commit hash by running `git log` copy the hash and run

git revert <commit hash>
 -->

Let's take a step back and think about what it's doing
If you've used github coplt, it 8ises the context of the repo to make suggestions

In the cli you're in a diff env you want to know shell commands, gh commands, git commands so behind the scenes we're telling the LLM to use those as its context and not your code. 

Now that we know this, let's look at a few moe examples and get an idea of what is happening behind the scenes

---
layout: fact
---
# How does Copilot in the CLI work? 🤔
<img src="https://media.giphy.com/media/qRVDIxBnu57gP0Jkg6/giphy-downsized-large.gif" alt="a man looking under the hhood of a car" />

<!--
Ask Andrew what's happening under the hood
-->

---
layout: section
---

# Top Questions about using the terminal
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
