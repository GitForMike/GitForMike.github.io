---
title: How to add my current project to an already existing GitHub repository
---

Run below commands.

```bash
$ git init
$ git add .
$ git commit -m "my commit"
$ git remote set-url origin git@github.com:username/repo.git
$ git push origin main
```