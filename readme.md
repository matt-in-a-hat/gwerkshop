# Git Werkshop

https://www.notion.so/voyagestudio/Git-workflow-f18fd352d69f429c8d76212da63fa041?pm=c

## Workshop to (hopefully) cover:
- Example run through of our process
  - fetch, branch, ga-p, git mv, commit, rebase -i (reorder, edit, squash), PR template, pre-merge rebase, --force-with-lease, merge
- examples of sticky situations
  - remote branch has conflicting updates
  - develop has conflicts (maybe an example of if you're seeing the same conflict multiple times in rebase, what went wrong)
  - hotfix needs cherry-pick to master, with conflicts
- multiple remotes e.g. if cloned open-source module before fork
- Run through commands & useful tools? git diff, git show, git log -p, git reflog, " -- files" (log, checkout, etc)
- general tips:
  - Create branches. Unsure? Stick it on a branch. Delete once all clean.

## Useful aliases I use (#lazy)

- alias git="hub" # ZSH plugin
- alias gs="git status"
- alias ga="git add"
- alias ga-p="git add --patch"
- alias gap="git add --patch"
- alias gfr="git fetch && git rebase"
- alias grc="git rebase --continue"
- alias gra="git rebase --abort"
- alias gcd="git checkout develop"
- alias grd="git rebase develop"
- alias gc="git commit -v"
- alias gco="git checkout"
- alias gca="git commit --amend"
- alias gcp="git cherry-pick"
- alias gcpc="git cherry-pick --continue"
- alias gcpa="git cherry-pick --abort"
- alias gwip='git commit --no-verify -m "--wip-- [skip ci]"' # Useful for those times you just need to drop what you're in the middle of and go test a different branch (or go home).

### Other useful configuration

Set your editor e.g. vs code: `git config --global core.editor "code -w"`

Set push behaviour so that `git push -u` will create & track an upstream branch with the same name as current branch: `git config --global push.default=current`

I also use `brew install diff-so-fancy` for `git diff`.

My `git config --global -l` looks like
```
user.name=Matt Lang
user.email=[snip]
color.ui=true
color.diff.whitespace=red reverse
core.editor=code -w
push.default=current
pager.diff=diff-so-fancy | less --tabs=1,5 -RFX
pager.show=diff-so-fancy | less --tabs=1,5 -RFX
pull.rebase=true
init.defaultbranch=main
credential.helper=osxkeychain
diff.lockb.textconv=bun
diff.lockb.binary=true
```

### More complex commands that I don't tend to use but could come in handy:

Show git log with a simple sort of branch graph beside
`alias glp="git log --graph --pretty='format:%C(yellow)%h%Cblue%d%Creset %s %C(white) %an, %ar%Creset'"`

Show any branches that are ahead/behind
`alias gbs="git branch -v | grep -E 'ahead|behind' | sed -E 's/[ *]\s(\S*).*(\[(ahead|behind)[^\]]*\]).*/\1 \2/g'"`

Show any branches that are not synced to a remote
`alias gbd="git for-each-ref --format='%(refname:short) %(upstream)' refs/heads | awk '$2 !~/^refs\/remotes/'"`


## Some content to change later

a
b
c
d
e
f
g
h
i
j
k
l
m
n
o
p
q
r
s
t
u
v
w
x
y
z
