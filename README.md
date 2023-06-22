# Dotfiles

simple dotfiles management

## Install

Recommended steps:

1. copy ~/.dotfiles/bin/dotfiles to ~/.local/bin
2. update your shell's PATH to include ~/.local/bin

## Setup

1. initialize your dotfiles repo: `dotfiles init`
2. setup remote: `dotfiles remote add origin git://example`
3. add your dot files: `dotfiles add .foo .bar`
4. commit: `dotfiles commit`
5. push: `dotfiles push`

## Synchronizing Across Multiple Devices

This setup uses branches to manage device specific dot files.

Here's a simple merging strategy that preserves files only existing
in the branch for your device while pulling in the latest changes
from the main branch:

```
dotfiles checkout DEVICE_NAME
dotfiles checkout -b temp
dotfiles merge master
dotfiles checkout -
dotfiles merge temp
dotfiles branch -D temp
```

For simple changes, you can use cherry pick to merge changes from
one branch into another:

```
dotfiles cherry-pick ...
```

## Restore

To restore a dotfiles repo from scratch:

```
mkdir ~/.dotfiles/ # only necessary when not starting from this template
dotfiles clone [GIT-REMOTE] [DEVICE_NAME]
e.g.
dotfiles clone git@gitlab.cas.org:kxw29/dotfiles.git kxw29-desktop.formulations.cloud.cas.org
```
