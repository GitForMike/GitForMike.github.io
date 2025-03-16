---
title: How to add my current project to an already existing GitHub repository
---

Run below commands.

```bash
$ git init
$ git add .
$ git commit -m "my commit"
$ git remote add origin git@github.com:username/repo.git
$ git branch --set-upstream-to=origin/main main
$ git pull --rebase
#(Resolve conflict if needed)
$ git push origin main
```