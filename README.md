# Dotfiles

simple dotfiles kit

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

This setup relies on branches to manage device specific dot files.

A simple approach is to have a main branch with common files shared
across devices:

```
dotfiles checkout DEVICE_BRANCH
dotfiles merge MAIN_BRANCH
```

## Restore

To restore a dotfiles repo from scratch:

```
mkdir ~/.dotfiles/ # only necessary when not starting from this template
dotfiles clone GIT-REMOTE [BRANCH_NAME]
e.g.
dotfiles clone git@gitlab.com:kevinrw/dotfiles.git zenbook
```

## Credits

Inspired by a combination of [vcsh](https://github.com/RichiH/vcsh) and this elegant
[approach](https://www.atlassian.com/git/tutorials/dotfiles).
