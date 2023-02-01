---
title: "Git"
date: 2023-02-01T00:25:52+01:00
draft: false
---

## Git log
### See single commit info
```fish
git log -n 1 --decorate
```

### Compact tree view
```fish
git log --graph --decorate
```

## Stash

- Default stash is `stash@{0}`

### General info
```fish
git stash show stash@{N}
```

### Diff the stash will introduce
```fish
git stash show -p stash@{N}
```

### Diff with branch
```fish
git diff stash stash@{N} branch
```
