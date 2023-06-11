# emacspro

This repository provides a simple `emacspro` bash script for running Emacs with
named profiles.

## Motivation

Emacs 29 added a `--init-directory` command line option. This option allows you
to specify a directory to load your Emacs configuration from. This is useful
for running Emacs with different configurations, but you have to remember to
pass the `--init-directory` option every time you open Emacs.

The `emacspro` script provides a simple way to run Emacs with different configs.
It allows you to manage multiple named profiles in its home directory, defined
by the `EMACSPRO_HOME` environment variable, and then run Emacs with a single
named profile, defined by the`EMACSPRO_PROFILE`environment variable.

## Usage

First, clone this repository someplace (here `~/src`):

```shell
cd ~/src
git clone https://github.com/mojochao/emacspro.git
```

Next, add its `bin` directory to your `PATH`.

```shell
export PATH=$PATH:~/src/emacspro/bin
```

Finally, run `emacspro -h` to display usage info.

```shell
$ emacspro
usage: emacspro -h            --  show help
       emacspro -c            --  show emacspro config
       emacspro -d            --  show profiles directory
       emacspro -l            --  list profiles
       emacspro -a NAME PATH  --  add profile
       emacspro -r NAME       --  remove profile
       emacspro [...]         --  open files in emacs with profile

config: EMACSPRO_HOME     --  directory where profiles are stored (default: ~/.local/share/emacspro)
        EMACSPRO_PROFILE  --  profile to use (default: default)
```

If extra lazy, define an alias in your shell config.

```shell
alias ep=emacspro
```
