---
type:
  - permanent
tags:
  - tools
---
This method involves adding some conditions to global git config. Then within each git repo, it will automatically figure out which email to use based on the path.

By default, the global git config looked something like this for me.

```bash
# ~/.gitconfig

[user]
    email = personal@email.com
    name = Hao Dong
```

### 1. Rename ".gitconfig" to ".gitconfig-personal"

Rename the global config to `~/.gitconfig-personal` using the following command. It will now be our new config for any personal projects.

```bash
mv .gitconfig .gitconfig-personal
```

Don't worry, we will add the global config back later.

### 2. Create ".gitconfig-work"

Create the new config file for work.

```bash
touch ~/.gitconfig-work
```

Then add the following into the config file.

```bash
# ~/.gitconfig-work

[user]
    email = work@email.com
    name = Hao Dong
```

### 3. Create a new ".gitconfig"

Add a new global `.gitconfig` file, this will point to the other two custom config files.

```bash
touch ~/.gitconfig
```

Then add the following into the global config file.

```bash
# ~/.gitconfig

[includeIf "gitdir:~/work/**"]
    path = .gitconfig-work
[includeIf "gitdir:~/personal/**"]
    path = .gitconfig-personal
```

Source: [https://git-scm.com/docs/git-config#_includes](https://git-scm.com/docs/git-config#_includes)

