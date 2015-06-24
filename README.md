# Git `master` Class

Hellow from GitHub where spelin gi s optional

"It's just version control." Or is it? When I started using `git-svn` more than
five years ago, I never imagined how fundamentally Git would change the way I
develop software. This session will cast new light on the basic Git commands
you already know as a first step into a hands-on exploration of the more
advanced tools at our disposal to develop software on our terms. Topics covered
will include local and distributed workflows, history inspection and
manipulation, and a glimpse into the power available through tools like
filter-branch`.

## Agenda

0:00 Introductions
0:15 Git Environment
0:30 git init & Core Concepts
1:20 <Break>
1:30 Local Workflow
1:45 git reflog
2:00 git reset
2:15 Patchwise Operations
2:25 Rewriting History
2:40 <Break>
2:50 Remotes
3:00 Remote Workflow
3:30 Bisect
3:40 Filter Branch
3:50 Q&A
4:00 <Fin>

## Keith Dahlby

* E-Commerce Architect @ Motorsport Aftermarket Group
* https://github.com/dahlbyk/posh-git
* https://github.com/libgit2/libgit2sharp
* Go Cyclones!
* @dahlbyk

## Git Environment

### Configuration

- `git help config`
- Scopes
  - Repository (`[--local]`) in `.git/config`
  - User (`--global`) in `$XDG_CONFIG_HOME/git/config` or `~/.gitconfig`
  - System (`--system`) in `$GIT_INSTALL_DIR/etc/gitconfig`
- `git config -e <scope>`

```
# git config core.editor vim
[core]
	editor = vim

# git config branch.master.rebase true
[branch "master"]
	remote = origin
	merge = refs/heads/master
	rebase = true
```

#### Suggestions

- `diff.renames = copies`
- `difftool.prompt = false`
- `mergetool.prompt = false`
- `mergetool.keepBackup = false`
- `help.autocorrect = 5`
- `log.date = relative`

### Aliases

- `git config alias.ds "diff --stat"
- `git ds` => `git diff --stat`
- `git ds dev` => `git diff

#### Suggestions

- `alias.lg = log --oneline --decorate ----graph
- `alias.new = log --oneline --decorate --reverse master..`
- http://bit.ly/better-git-svn

## git init & Core Concepts

### Working Directory

### Index

### Commit

#### Blob

#### Tree

#### Metadata

### HEAD

### Checkout

### History

## Local Workflow

### Branching

1. Keep `master` clean!
2. Create new topic branches from `master`
   - `git checkout master -b topic`
3. Commit more than feels natural

### Stash

### Temporary Commits

## git reflog

## git reset

### `git reset [<commit>] [--mode]`

### `git reset [<commit>] -- <paths>`

## Patchwise Operations

- `git add -p`
- `git reset -p`
- `git checkout -p`
- `git stash -p`

## Rewriting History

### git commit --amend

### git cherry-pick

- How might a commit be "moved" to the correct branch?

### git rebase

### git rebase --interactive

#### --autosquash

- `rebase.autosquash = true`

## Remotes

## Remote Workflow

### Push

- `push.default = upstream`

### Pull

### up & pub

- `alias.up = !git fetch origin --prune && git rebase origin/master && git push . origin/master:master 2> /dev/null`
- `alias.pub = !git push origin HEAD:master && git push . HEAD:master && git checkout master`

## Bisect

## Filter Branch

