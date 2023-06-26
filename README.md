# Dotfiles

simple dotfiles kit

Simple dot file management using only git and a small wrapper
shell script. No symlinking. Explicit tracking. All packaged into
distributable kit that can be easily deployed to just about any device.

## Requirements

* git
* bash

## Install

There's two different approaches you can take.

1. Install this repository as a template.
2. Use this repository as a reference and handle the installation in
   a more manual fashion.

Recommended steps to install as a template:

1. clone this repository
2. copy all the files and directories into your $HOME directory
3. copy ~/.dotfiles/bin/dotfiles to ~/.local/bin
4. update your shell's PATH to include ~/.local/bin

## Setup

1. initialize your dotfiles repo: `dotfiles init`
2. setup remote: `dotfiles remote add origin git://example`
3. add your dot files: `dotfiles add .foo .bar`
4. commit changes: `dotfiles commit`
5. push changes: `dotfiles push`

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
