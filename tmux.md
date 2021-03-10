---
title: Tmux
date: 2021-02-20 14:31:24
icon: icon-tmux
background: bg-green-600
tags:
categories:
    - Linux Command
intro: |
    Tmux cheat sheet quick reference of most commonly used shortcuts and commands
---



Tmux CLI {.cols-3}
-------

### New session  {.row-span-2}
Start a new session
```shell script
$ tmux
```
Start a new named session
```shell script
$ tmux new -s myname
```
Show all sessions
```shell script
$ tmux ls
```

### Attach session
Attach to last session
```shell script
$ tmux a
```
Attach to named
```shell script
$ tmux a -t myname
```


### Kill session  {.row-span-2}
Kill a session by name
```shell script
$ tmux kill-ses -t myname
```
Kill sessions but the current
```shell script
$ tmux kill-ses -a
```
Kill sessions but 'myname'
```shell script
$ tmux kill-ses -a -t myname
```


### Tmux help
```shell script
$ tmux info
```

### Config
Reload config
```shell script
$ tmux source-file ~/.tmu­x.conf
```
Show config
```shell script
$ tmux show-options -g
```



### Copy Mode  
| Command             | Description                  |
|---------------------|------------------------------|
| `Ctrl+b` `[`        | Enter copy mode           |
| `<Space>`      | Start selection                         |
| `Enter`         | Copy selection                          |
| `q`                 | Quit copy mode               |
| `Ctrl+b` `]`        | Paste contents of buffer_0 |
{.shortcuts}


Mainly works like selecting text in [Vim](/vim#motions)





Tmux shortcuts {.cols-3}
--------------

### Getting started {.secondary}
| Shortcuts           | Description                  |
|---------------------|------------------------------|
| `Ctrl+b` `?`        | List all shortcuts           |
{.shortcuts .show-header}

<br/>

----

Show every session, window, pane, etc.
```shell script
$ tmux info
```



### Panes (Splits) {.row-span-2}

| Shortcuts                | Description  |
|--------------------------|--------------|
| `Ctrl+b` `"` _/_ `%`            | Split Horiz/Vert|
| `Ctrl+b` `!`             | Pane -> Window |
| `Ctrl+b` `x`             | Kill pane        |
| `Ctrl+b` <arrow\> | Navigate panes |
| `Ctrl+b` <h j k l\>       | Goto _(vim-style)_|
| `Ctrl+b` `{` _/_ `}`             | Previous/Next pane    |
| `Ctrl+b` `o`             | Goto next panes      |
| `Ctrl+b` `z`             | toggle full-screen     |
| `Ctrl+b` `;`             | Toggle Last pane        |
| `Ctrl+b` `q`             | Show numbers       |
| `Ctrl+b` `q` `0`...`9` | Goto # pane |
{.shortcuts}



### Window (Tabs) {.row-span-2}
| -                  | -                              |
|--------------------|--------------------------------|
| `Ctrl+b` `c` _/_ `N`       | Create window                  |
| `Ctrl+b` `p` _/_ `n`      | Previous/Next window                |
| `Ctrl+b` `"` _/_ `%`            | Split Horiz/Vert|
| `Ctrl+b` `w`       | List window                  |
| `Ctrl+b` `,`       | Rename window                  |
| `Ctrl+b` `f`       | Find window                  |
| `Ctrl+b` `l`       | Last window                  |
| `Ctrl+b` `.`       | Move window                  |
| `Ctrl+b` `&`       | Close window           |
| `Ctrl+b` `0`...`9` | Goto # window |
{.shortcuts}



### Session (Set of Windows)
| -              | -                        |
|----------------|--------------------------|
| `Ctrl+b` `d` | <red>Detach from session</red>      |
| `Ctrl+b` `s` | Show all sessions        |
| `Ctrl+b` `$` | Rename session           |
| `Ctrl+b` `(` _/_ `)` | Previous/Next session |
{.shortcuts}



Command Mode {.cols-3}
-----------

### Usage {.secondary}
| Command             | Description                  |
|---------------------|------------------------------|
| `Ctrl+b` `:`        | Enter command mode           |
{.shortcuts}


### Resizing 

| Command             | Description                  |
|---------------------|------------------------------|
| `resize-pane -D 20`  | Resize down                  |
| `resize-pane -U 20`  | Resize up                    |
| `resize-pane -L 20`  | Resize left                  |
| `resize-pane -R 20`  | Resize right                 |


### Listing

| Command             | Description                  |
|---------------------|------------------------------|
| `list-keys`           | All commands       |
| `list-panes`         | All panes |
| `list-windows`         | All Windows |


### Copying

| Command               | Description           |
|-----------------------|-----------------------|
| `list-buffers`        | List all buffers      |
| `show-buffer`         | Show #0 contents      |
| `capture-pane`        | Copy of pane          |
| `choose-buffer`       | Show and paste        |
| `save-buffer a.txt`   | Save to file          |
| `delete-buffer -b 1`  | Delete buffer 1       |


### Setting
| Command               | Description           |
|-----------------------|-----------------------|
`set -g OPTION` | Set for all sessions
`setw -g OPTION` | Set for all windows
`setw -g mode-keys vi` | Enable vi-mode
`set -g prefix C-a` | Set prefix


### Misc
| Command             | Description                  |
|---------------------|------------------------------|
| `swap-pane -s 3 -t 1`| Swap pane  |
| `swap-window -t -1`| Move to left  |
| `setw synchronize-panes`| Sync Panes |
| `join-pane -t :#` | Join pane |