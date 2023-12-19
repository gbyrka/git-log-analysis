### Latest contributor activity
```sh
git log -4 --author="Grzegorz Byrka"
```

### Branch history presented in the graphic way
```sh
git log --graph --oneline --decorate
```

### The history of merges and the history without merges
```sh
git log --no-merges
git log --merges 
```

### First commits to the repository
```sh
git log --reverse
```

### Most active contributors
```sh
git shortlog -sen --no-merges 
git shortlog -sn --no-merges 

git shortlog -sn --no-merges --after="2019-1-1"
git shortlog -sn --no-merges --before="2019-1-1" --after="2018-1-1"
```
### Date range of the contributor activity
```sh
git log --pretty=format:"%ad%" --author="Grzegorz Byrka" --reverse | head -n 3
git log --pretty=format:"%ad%" --author="Grzegorz Byrka" | head -n 3
```

### Files edited most often
```sh
git log --name-only --pretty=format: | sort | uniq -c | sort -nr | head -n 20
git log --before="2019-1-1" --after="2018-1-1" --name-only --pretty=format: | sort | uniq -c | sort -nr | head -n 20
git log --author="Grzegorz Byrka" --name-only --pretty=format: | sort | uniq -c | sort -nr | head -n 20
```

### Basic project info
```sh
phploc
```
or http://cloc.sourceforge.net/

### Exact date checkout (a.k.a. Time travel)
```sh
git checkout 'master@{2019-01-01 00:00:01}'
```

This method uses the reflog to find the commit in your history. By default these entries expire after 90 days. Although the syntax for using the reflog is less verbose you can only go back 90 days.

```sh
git checkout `git rev-list -n 1 --first-parent --before="2019-01-01 00:01" master`
```


## Git Static Analyzer
Some of the above is automated here: https://github.com/gbyrka/git-static-analyzer

