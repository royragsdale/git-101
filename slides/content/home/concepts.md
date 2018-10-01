+++
weight = 20
+++

{{% section %}}

# The Nouns

---

## repository

## branch

## commit

## remote

---
# repository

Typically this will map to a project.

Stores files and metadata.

---
# repository
> basically a .git directory with subdirectories for objects, refs/heads,
> refs/tags, and template files. An initial HEAD file that references the HEAD of
> the master branch is also created.

[reference](https://git-scm.com/docs/git-init)


```
$ ls .git/
branches  COMMIT_EDITMSG  config  description  HEAD
hooks  index  info  logs objects  ORIG_HEAD  refs
```

A head is simply a reference to a commit object. Each head has a name.

---
# branch

---
# commit

---
# Remote



{{% /section %}}
