# GitCommandsConfigs

`.gitconfig` and git commands I use. 👉

## `.gitconfig` 🔧

Open `.gitconfig`! 😉

If you use Windows, make sure you setup the following section to the corresponding variables:

```bash
[user]
	name = %USERNAME%
	email = %EMAIL%
[core]
	excludesFile = %USERNAME%\\.gitignore
```

## Git Commands 🌿

### Force push

```bash
push --force origin
```

### Restore deleted branch

```bash
gitk --reflog
```

### Force checkout branch, when file conflict appears

```bash
git checkout -f another-branch 
```

### Git tree

```bash
git log --graph --pretty=oneline --abbrev-commit  
```

### Beautiful Git tree

```bash
git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(green)%C(bold)%ad%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --date=short 
```

### Prune tags

```bash 
git fetch --prune --prune-tags
```

### Delete all merged branches into `master` and `develop`

```bash
git branch --merged | grep  -v '\\*\\|master\\|develop' | xargs -n 1 -r git branch -d
```

### Cleanup `develop` branch

```bash
git checkout develop | git delete-merged | git remote prune origin | git prune | git prune-tags | git clean -df | git gc
```

### Cleanup `master` branch

```bash
git checkout master | git delete-merged | git remote prune origin | git prune | git prune-tags | git clean -df | git gc
```

### Show current branch

```bash
git rev-parse --abbrev-ref HEAD
```

### Rebase on `develop`

```bash
git pull --rebase origin develop
```

### Rebase on `master`

```bash
git pull --rebase origin master
```