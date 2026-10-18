# GitHub Commands Learning

**Start Editing Date:** 18-10-2026

**Tags:** #github #git #gh #dev #mouse-free #keyboard-only

Creating a cheat sheet for my development on different languages. Here is the starting point that using the GitHub to keep track on the progress. By creating a cheat sheet is helping to understand and remember the code quickly.

[Marz's GitHub Cheat Sheet](https://github.com/martin-marzzz/git-vim-md-cheatSheet#github-commands)

---

## Contents 

I saw YouTube video online, there are people creating contents use keyboard to edit files and organise folder that I feel so cool. Therefore I start learning how to not touching the mouse then do the development. I am trying to get rid of VS Code and change to use lazyvim and learn git command line work. So there are few more cheat sheets about nvim and markdown file editing, it will be more on other learning journey on other coding languages as well. 

Starting with creating the new repo, before that it needs to connect the local machine to GitHub server. I am not showing in here, basically, just create the authentication key on Git then set the connection to computer.

### What is a repo?

Repo is repository, that is a project folder that git keeps track on. It is not only holding the files, but also the full history of every change the user have committed. Hence, user can check back on what changes made and go back when it is needed. It is also call the **Version Control**.

Initiate the new repo, just like normal make a new dir as a folder and name it with meaning. Use git init and set as the main. 

```bash
mkdir my-repo && cd my-repo # make new folder and go into it
git init -b main            # turn it into a git repo
```

Then it comes to an important function of git, add and commit. It like making a saving stage on the book that telling GitHub to made changes(create, delete or changes).

```bash
git add .
git commit -m "Commons on the git add"

# not needed for the init step
git push        # actual pushing the files and modification to the server
```
