---
title: "Fish"
date: 2023-02-01T00:32:11+01:00
draft: false
---

Configuration help for fish

## config.fish

### set path
[doc](https://fishshell.com/docs/current/cmds/fish_add_path.html)
```fish
fish_add_path /path/to/bin
```

### Change path shortening threshold
[doc](https://fishshell.com/docs/current/cmds/prompt_pwd.html)
```fish
set -g fish_prompt_pwd_dir_length 10
```

### Make use of !!
[source](https://superuser.com/questions/719531/what-is-the-equivalent-of-bashs-and-in-the-fish-shell)
-> [(see also)](https://github.com/fish-shell/fish-shell/wiki/Bash-Style-Command-Substitution-and-Chaining-(!!-!$))
```fish
function bind_bang
    switch (commandline -t)[-1]
        case "!"
            commandline -t -- $history[1]
            commandline -f repaint
        case "*"
            commandline -i !
    end
end

function bind_dollar
    switch (commandline -t)[-1]
        case "!"
            commandline -f backward-delete-char history-token-search-backward
        case "*"
            commandline -i '$'
    end
end

function fish_user_key_bindings
    bind ! bind_bang
    bind '$' bind_dollar
end
```
