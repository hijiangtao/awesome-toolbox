# Git Alias Setup

* .gitconfig

```
[alias]
    a = add
    ad = add -A

    # list branches sorted by last modified
    b = "!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"
    br = branch
    co = checkout
    cob = checkout -b
    
    c = commit --verbose
    ca = commit -a --verbose
    cm = commit -m
    cam = commit -a -m

    d = diff
    ds = diff --stat
    dc = diff --cached

    # the last commit
    last = log -1 HEAD
    # list aliases
    la = "!git config -l | grep alias | cut -c 7-"
    # one-line log
    l = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

    rao = remote add origin
    st = status
```

* .bashrc file (for calling with `g<alias>`)

```
if [ -f /etc/bash_completion ] && ! shopt -oq posix; then
    . /etc/bash_completion
    . /usr/share/bash-completion/completions/git
fi


function_exists() {
    declare -f -F $1 > /dev/null
    return $?
}

for al in `__git_aliases`; do
    alias g$al="git $al"

    complete_func=_git_$(__git_aliased_command $al)
    function_exists $complete_fnc && __git_complete g$al $complete_func
done
```