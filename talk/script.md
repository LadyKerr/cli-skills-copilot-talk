## Intro
<< Add stuff from the copilot cli doc >>

## Installation 

To install gh copilot cli extension, ensure that you have `gh cli` on your machine. You can installed the gh cli with homebrew, chocolatey or any other package manager based on your os.

After your install you will be asked to authenticate with OAuth app via web browser. Once that's complete, you can install gh copilot cli with the following command: 

```
gh cli extension install github/gh-copilot

```

Then you'll be all set and ready to use copilot in the command line.
## How does it work?

If we run the command `gh copilot` we will get a list of commands that's available, let's try that out and see

```
gh copilot
Your AI command line copilot.

Usage:
  copilot [command]

Available Commands:
  explain     Explain a command
  suggest     Suggest a command

Flags:
  -h, --help      help for copilot
  -v, --version   version for copilot

Use "copilot [command] --help" for more information about a command.


```
## How to use copilot cli 

So when it comes to using copilot for cli the main thing to remember is 

```
gh copilot <command> <your request>

```

Like I said earlier, `gh coilot cli` has 2 main commands that you can use: `suggest` and `explain` these commands is how you'll get a response from each session you have with copilot cli. Let me show you what I mean.

Let's say for example that I want to create a new folder but I do't remember that command to do so. I can ask copilot cli like so:

`gh copilot suggest create a new folder`

Oh! yes, of course, `mkdir folder_name`
Ok, cool, I love that I didn't have to go to google and ask that, just did it from my terminal, asked copilot for help and be on my way

Before I start coding, I want to initialize git `git init`

## Prompting copilot cli to get the right stuff

Let's create a new react project with nextjs. I remember learning that create-react-app was no more and I was like whoa! LOL It was absolutely such sad news to me, primarily because it was easy to remember, now every time I want to start a new react project, I have to ask my ai friend to help me out . . .

```
gh copilot suggest create new react project

>> npx create-react-app my-app

```

This returns an outdated command . . . uh oh, lemme get a revision real quick 
So, Im going to revise it by saying 

```
Revise command: create-react-app is outdated

>> npx degit "https://github.com/facebook/create-react-app#readme" my-app


```

Ok it doesn't seem to understand what I'm trying to accomplish and that wasn't really a revision lol. Lemme be more clear in what I want because what I really want is to create a new nextjs project and I'll use React on the frontend:''

```
Revise command: create a new next project

>> npx create-next-app my-app

```


Ok there we go. 

I wanted to show you this so you understand that `gh copilot` is not magic and it cannot read your mind. It's a tool there to help you when you need it and you have to prompt it properly to get the response that you want. It's also a great way to use the tool to jog your memory instead of going down browser search rabbit holes. 

So you kind of have to remember that communicating effectively with copilot cli is essential to your success. 

## Pushing a local folder to a GitHub repo 

Now let's create a gh repo and push this folder...

`gh repo create` is how we create a github repo with the gh cli and then we can push our folder to that repo . . . I often forget the commands to run to do that so let's ask copilot

```
gh copilot suggest push a local folder to a github repo

Suggestion/Solution
git remote add origin https://github.com/LadyKerr/techy-trends.git

git push -u origin main

```

While Github copilot is not magic, you must remember that the magic is in the prompt. 
Now let's take a look at another cli example. 

## Remove a file from a commit while keeping the original commit 

Im going to get out of this folder and create a new one and initialize git:

`mkdir demo && cd demo && git init`

Now let's say I want to create two files, Im going to call one `demo.md` and the other one `mistake.md` . . . I honestly forget how to create new files all the time so Im going to ask how I can do this

`gh copilot suggest create two files and commit them`

I'm kinda getting tired of typing `gh copilot suggest` all the time, so let me set an alias real quick to make this process go a lil faster:

```

gh copilot suggest create an alias ghs for gh copilot suggest and add to zshrc file

echo 'alias ghs="gh copilot suggest"' >> ~/.zshrc && source ~/.zshrc

```

Ok so now if you see me running `ghs` just know its an alias for `gh copilot suggest` let's keep going.

So I created and committed those two files before, let's modify both files real quick and commit them.

```
echo "I like using the gh cli" > demo.md
echo "I'm at universe 23!" > mistake.txt

```

`git add . `
`git commit -m "updated files"`

You know how sometimes you're working and you make changes to multiple files - files you didn't intend to edit lol - and you wanted to have each file in a separate commit to track the work that was done BUT you commit all the changed files in one commit and you want to remove the unneeded file? That was a mouthful butt I didn't mean to commit `mistake.md` at the same time but I do want to keep the commit message so how do I remove that file and keep the commit message?

I don't know this one so, :D let's ask copilot! 

but I made a mistake and I need to delete the changes from `mistake.md` from the last commit while keeping the commit message. Honestly have no idea how to do that so let's ask copilot. 

`ghs remove mistake.md from last commit keeping commit message`

Seems legit. I don't understand this really so let's ask it to explain what is happening here before I run it.

Ok nice explanation, let's copy these commands and run it!

```
git rm --cached mistake.md
git commit --amend --no-edit

```

Nice now if I run `git log` we should see our two commit messages . . . .

and if I run git status, I should see `mistake.md` unstaged and uncommitted. When we look in VsCode, `markdown.md` is green which means it's untracked and uncommitted. Pretty cool. 

Let's keep going! 💃🏼

## Convert markdown to word doc 

I often use an online tool to convert markdown files to word docs but If you ever want to convert a markdown document to a word doc, we can ask copilot how do to do via cli:

```
gh copilot suggest convert demo.md to docx

```

If I copy this command and run it, I get an error because I'm using `zsh` . Let's ask copilot how to add:

```
gh copilot suggest how to add pandoc to zsh

SUGGESTION:

echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc && brew install pandoc

```

It. gave me 3 commands as you can see - adding pandoc to my path, sourcing zshrc so it's ready to be used and installing pandoc with homebrew. Let's copy this and run it.

Now that that's done, I can retry the command to convert `md` to `docx` 

Great! Now that that's done, I can run ls to see a list of my files and there's the new `demo.docx` file, I can open it up and it has 

## Explain a dangerous command

I came across a shell command online that looked a lil iffy. Let me ask copilot chat wat it does before I even think of copy/pasta:

```
gh copilot explain chmod -r 777 /

```

Oof, from this explanation is is one of the most dangerous commands you can run on your machine. I'm so glad I got an explanation before I thought of even running this. This command would allow open access to all files of your computer exposing your system to potential attacks. You would have given read, write and execute permissions at the owner, group, and other permission levels. WILD. 

Copilot CLI is a great tool for learning more about commands and what they mean and do right in your terminal. 

Now, let's take a look at some of the most asked questions about using CLI.

I have 10 questions here that folks typically ask when it comes to using the terminal so let's go through them and THENN, if we have time remaining, I'd love to get a suggestion from the audience about something to ask copilot cli.

## How do I delete git Branch Locally and remotely

## How do I kill processes with open files that have been deleted

## How do I Modify existing, unpushed commit messages?

## How do I Check if a directory exists in shell script?

## How do I Rename a local git branch

## How do I Post JSON data with cURL

## How do I Undo most recent local git commit 

## How do I make git forget about a file that was tracked, but is now in .gitignore? 

## How do I find and kill processes locking port 3000 on Mac?

## How do I exit vim? 

Now that I've shown you the abilities of GitHub copilot cli, are you ready to use it? 
Im looking for at least 1 suggestion from someone in the audience . . . any takers? Let's ask else something live! 

If no one ask, show this example: 

### Convert video to gif 

If you create content for developer son the internet and post to blogs like dev.to you may often need to convert a mp4 video to a gif. Typically I use an online video to gif converter but is there a way to do this in the command line? Let's ask copilot

```
gh copilot suggest convert mp4 to gif

>>> ffmpeg -i input.mp4 -vf "scale=640:-1" -r 15 -f gif output.gif
>>
>>Explain
