## Git Hidden Folder

There is a hidden folder called `.git` which tells you that our project is a git repo.

If we wanted to create a git repo in a new project we'd create the folder and then intialize that repo using 
`git init`

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
# makes changes to readme.md
git commit -a -m "add readme file"
```
## Cloning

We can clone three ways: HTTPS, SSH, GitHub CLI

Since we are using GitHub Codespaces we'll create a temporary directory in our workspace.

```sh
mkdir /workspace/tmp
cd /worspace/tmp
```
### HTTPS

```sh
git clone https://github.com/lestergtsantos/Github-Examples.git
```

> You'll need to generate a Personal Access Token )PAT)

https://github.com/settings/token

You will use the PAT as your password when you login

- Give it access to Contents for Commits

### SSH

```sh
git clone git@github.com:lestergtsantos/Github-Examples.git
```

We will need to create our own SSH rsa key pair

```sh
sshe-keygen -t rsa
```
We can test our connection here:

```
ssh -T git@github.com
```

### GitHub CLI

Install the CLI

eg. Linux (Ubuntu)

```sh
type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

```sh
gh auth login
gh repo clone lestergtsantos/Github-Examples
```
## Commits

When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice.

```sh
git commit
```

Set the global editor

```sh
git config --global core.editor emacs
```

Make a commit and commit message without opening an editor

```sh
git commit -m "add another exclamation"
```

## Branches

List of branches

```sh
git branch
```

Create a new branch

```sh
git branch branch-name
```

Checkout the branch

```sh
git checkout dev
```


## Remotes

## Stashing

## Merging

## Add

When wwe want to stage changed that will be included in the commit. We can use the `.` to add all possible files.

```sh
git add Readem.md
git add .
```

## Reset

Reset allow syou to move Staged changes to be unstaged.
THis is useful when you want to rever all files not to be commited.

```sh
git add .
git reset
```

> git reset will revert a git add.

## Status

GIt status shows you what files will or will not be commited.

```sh
git status
```

## Gitconfig file

The gitconfig file is what stores your global configuration for git such as email, 
name, editor and more.

Showing the contents of our `.gitconfig` file

```sh
git config --list
```
When you firs install Git on a machine you are suppose to set up your
name and email.

```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Log

git log will show recent git commmits to the git tree.

```sh
git log
```
## Push

WHen we want to push a repo to our remote origin

```sh
git push
```
