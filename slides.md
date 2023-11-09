---
theme: mokkapps
title: GitHub Copilot for CLI
favicon: ""
layout: cover
lineNumbers: true
transition: fade
record: 'dev'
download: true
exportFilename: 'gh-copilot-cli'
export:
  format: pdf
  timeout: 30000
  dark: false
  withClicks: false
---

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

<img src="https://github.com/LadyKerr/mealmetrics-copilot/assets/47188731/d7630836-239f-441d-848c-a93c6dd35c52" alt="github copilot in the cli" width="600" />

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

GitHub Copilot in the CLI is designed to answer questions about:
- general shell commands
- git commands
- _gh_ cli commands

<br />

<img src="https://github.com/LadyKerr/mealmetrics-copilot/assets/47188731/c25d4257-3c75-4804-beb6-bf99f3795848" alt="github copilot in the cli" width="600" />

---
layout: intro
---

# Installation 🛠️
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

create your own alias for gh copilot commands

I'm using zsh so I ran:

```bash
alias copilot='gh copilot' ; echo 'alias copilot="gh copilot"' >> ~/.zshrc && source ~/.zshrc
alias gcs='gh copilot suggest' ^
alias gce='gh copilot explain' ^
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

You can also follow the on screen prompts if you run this command:

```bash
gh copilot explain
```

<br />
💡 the command you want to be explained must be in a string

<!--
There are 2 ways you can interact with copilot in the cli to explain a command:

Show: runing the command and following the on screen prompts
- gce
- enter flow
- follow on screen prompts to explain a command
- copy command above in the example bash and explain that 

Show: asking it the question at the same tume you run the command
- gce 'cd ~'

Point out the importance of placing the query in a string, otherwise copilot may not understand what you want, since it's expecting a string.

My favorite way to do it is to run the command and ask it the query at the same time
-->

---
layout: intro
---

# Suggest Command 🤖

this command is used to get suggestions for any shell, git or gh cli inquiry:

```bash
gh copilot suggest 'what you want to do' -t <git|gh|shell>

Example: gh copilot suggest 'install and configure git lfs' -t shell
```

you can also run:
```bash
gh copilot suggest
```

and follow the on screen prompts

<!--
There are 3 ways you can interact with copilot in the cli to get a suggestion:

Show: runing the command and following the on screen prompts
- gcs
- enter flow
- follow on screen prompts to suggest a command
- type: create a new codespace
- revise: create the codespace on the  main branch
- suggestion: gcs how to view codespaces in this repo
- run: gh codespace list
- copy command above in the example

Show: asking it a query and then selecting the type
- type  gcs create a new codespace
- copilot will respond with the suggestion
- click to explain the suggestion

Show: telling it the type while you ask the query
- gh gcs create a new codespace -t gh

My favorite way to do it is to give it the query and tell it the type of 
command at the same time with the -t flag
-->

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
transition: slide-left
---

## ok that was a lot of talking...

let's get into some demos 💃🏼

<img src="https://media.giphy.com/media/5q3NyUvgt1w9unrLJ9/giphy.gif" alt-="neicy nash saying time is ticking" />

---
layout: full
class: "text-center"
transition: slide-left
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
💡 communicating effectively with copilot cli is essential to your success

<!-- 
- gcs create a new react project named techy-trends
- revise: create react app is outdated
- that doesnt seem right, You know what actually what I really want is a new nextjs project where I'll the use react to build the UI
- revise: create a new nextjs project named techy-trends

When it comes to using copilot in the cli, much like copilot in general, make sure yo're asking for exactly what you need. The more specific you are the better your outcome will be. 

Let's take a look at another example.
-->

---
layout: full
class: "text-center"
transition: slide-left
---

# Push a local folder to a new GitHub repo 🗂️
We can create a GitHub repo with the cli 

```bash
gh copilot suggest 'push a local folder to a github repo'
```

<!-- 
I just created a folder, so let's push it to GitHub. How many of you forget how to do this?
Like, when you create the folder locally before creating the repo on GitHub and then you have to go back and forth between the browser and the terminal to figure out what to do next.

Ok, so with copilot in the cli i dont have to do that. 

So I know I can create a repo with gh cli: 
- gh repo create techy-trends --private
But how do I push this folder to the repo? Let's ask:
- gcs push a local folder to a github repo -t shell
- follow gh copilot suggestions
- run gh browse to open repo in browser

Sweet, that was a lot faster for me than going down the browser search rabbit hole

Alright, let's keep going. Im going to ask copilot to explain a command for me that I found online
 -->


---
layout: full
class: "text-center"
transition: slide-left
---

# Explain a dangerous command ⚠️
We can ask copilot cli to explain commands that appears simple enough, but are actually dangerous

```bash
gh copilot explain chmod -r 777 /
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
NEVER RUN THIS ONE YOUR MACHINE


<!-- 
So, I saw this command and was curious about what it did so I can ask
Copy command:
- gce 'chmod -r 777 /'

oh wow, that seems pretty dangerous. I'm glad I asked copilot to explain it to me before I ran it.
Imagine if you run a terminal command you have no idea about and it gives everyone read, write and cute permissions on your  machine. yikes, that would be bad.
 -->
---
layout: full
class: "text-center"
transition: slide-left
---

# Remove a file from a commit msg and <br/> keep the original commit msg 🧐
ever commit a file you didn't mean to add?

```bash
gh copilot suggest 'remove <filename> from last commit keeping commit message'

```
<!-- live terminal example here -->

<!-- show after the terminal demo -->

<!--  
create a new folder and initialize git: `mkdir demo && cd demo && git init`
create two new files: `touch demo.md && touch mistake.md`

commit both files: `git add . && git commit -m "initial commit"`

add content to both files:
echo "I like gh copilot cli" > demo.md
echo "I'm at gh universe '23!" > mistake.md

commit both files: `git add . && git commit -m "add content to both files"`

Now ask copilot to suggest how remove the file and keep the commit

ANSWER:
```bash
git reset --soft HEAD~1
git rm mistake.md
git commit -c ORIG_HEAD
```

Ask to explain commands
run commands
show changes in vscode or just run git log and git status

Works? Great! Say this:
And there we go! Whenever I run this demo it always feels so magical! I love that copilot knew to soft reset, remove the file, and then commit the changes with the original commit message.

Doesnt work? Run again and if still, Say this, and copy the command yourself:
If it doesnt work, run it again until you get the correct response. Otherwise, copy the command yourself and explain that LLMs sometimes get it wrong as well. 

-->

---
layout: full
class: "text-center"
transition: slide-left
---

# Download a Youtube Video 🤔
Did you know that you can download youtube videos with the cli?

```bash
github copilot suggest 'download youtube video'

```
<!-- live terminal example here -->

<!-- 
Ok so it tells me to use the youtube-dl cli program. Let's install it with homebrew and then try to download a video

- create a new terminal window and run the command below:
- brew install youtube-dl
While that's going, I wonder if copilot can get me a link to the repo for this program. Let's ask: gce 'get link to youtube-dl repo'

link to repo: https://github.com/ytdl-org/youtube-dl

Go to youtube and get a video link to download: https://www.youtube.com/watch?v=D-gkwzExddk&t=2s&ab_channel=GitHub 

Return to terminal where homebrew ran and run the command below:
- youtube-dl https://www.youtube.com/watch?v=D-gkwzExddk&t=2s&ab_channel=GitHub
-->

---
layout: image-left
image: https://media.giphy.com/media/qRVDIxBnu57gP0Jkg6/giphy-downsized-large.gif
---
# How does Copilot in the CLI work? 🤔
<img src="https://media.giphy.com/media/qRVDIxBnu57gP0Jkg6/giphy-downsized-large.gif" alt="a man looking under the hhood of a car" />

<!--
Let's take a step back and think about what it's doing
If you've used github copilot, it uses the context of the repo to make suggestions for your code

In the cli you're in a diff env with copilot that's specific to shell commands, gh commands, git commands so behind the scenes we're telling the LLM to use those as its context and not your code. 

Now that we know this, let's look at a few more examples and get an idea of what is happening behind the scenes
-->

---
layout: intro
class: "text-left"
---
# Behind Copilot in the CLI 👀

### Thread: conversation between you and copilot
### Turn: a single user mesage in a thread

❶ **User Input Prompt** (natural language prompts or questions) <br/>
❷ **LLM Analysis** (trained neural network finds response) <br/>
❸ **Response Generation** (gives a suggestion that you can copy) <br/>
❹ **Output Formatting** (syntax highlighting, indentations, etc) <br/>


<!--
thread is no different than a Slack thread: it is conversation that spans multiple messages going back and forth
turn is where the extension / integration makes a request and gets a response from the Copilot API for a new suggestion given the most recent revision and the past context
-->

---
layout: section
transition: slide-left
---

---
layout: full
class: "text-center"
transition: slide-left
---

#  ❓delete a git branch locally and remotely ❓


```bash
gh copilot suggest 'delete a git branch locally and remotely'
```
<!-- live terminal example here -->

<!-- show after the terminal demo -->
Repo: https://gh.io/mealmetrics-copilot

<!-- 
- dir: documents/demo 
- cd into mealmetrics-copilot
- run git branch to see list of branches locally
- run git branch -r to see list of branches remotely
- run gh copilot suggest 'delete a git branch locally and remotely'
- ask it to explain the command because what does remote_name mean?
- run the suggested command and delete branch copilot
- run git branch -r to see list of branches remotely & git branch to see list of branches locally
--> 

---
layout: full
class: "text-center"
transition: slide-left
---

# ❓ check if a directory exists in shell script ❓

 

```bash
git copilot suggest 'check if dir exist in shell script'
```
<!-- live terminal example here -->

<!-- 
run pwd 
copy dir link
pop in the code copilot gives
run

ANSWER:
Check if a directory exists:

  if [ -d /path/to/dir ]; then
  echo "Directory exists";
  fi

 -->

---
layout: full
class: "text-center"
transition: slide-left
---

# ❓ rename a local git branch ❓

```bash
gh copilot suggest 'rename a local git branch'
```

<!-- live terminal example here -->

<!-- 
cd into m

git checkout -b rename
git ranch -m <new-name>
 -->

---
layout: full
class: "text-center"
transition: slide-left
---

# ❓ see hidden files in current directory ❓

```bash
gh copilot suggest 'see hidden files in current directory'
```

<!-- live terminal example here -->

<!-- show after the terminal demo -->

---
layout: full
class: "text-center"
transition: slide-left
---

# ❓ exit vim ❓

```bash
gh copilot suggest 'how to exit vim'

```
<!-- live terminal example here -->

<!-- 
This would not be a copilot cli terminal demo if I didnt ask this one question
-->

---
layout: full
class: "text-center"
transition: fade
---

# ❓ give me a suggestion ❓
What would you like me to ask?

```bash
gh copilot suggest/explain ??
```
<!-- live terminal example here -->

---
layout: end
class: "image-center"
transition: fade
---
# ✨ Try it for yourself! ✨

 <img src="https://github.com/LadyKerr/mealmetrics-copilot/assets/47188731/3b56b485-6186-44f6-9ab7-34d34178cf3d" alt="github copilot in the cli qr code" />

---
layout: outro
---

Find me online [@itsthatladydev](https://itsthatlady.dev/mylinks/) 💃🏼
