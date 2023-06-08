# emacspro

This repository provides a simple `emacspro` bash script for running Emacs using
one or more profiles in the `~/.local/share/emacspro/profiles` directory and the
new `--init-directory` command line option present in Emacs 29 and later.

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

Finally, run Emacs using the `emacspro` wrapper script.
Use the `-h` option to display usage info.

```shell
$ emacspro -h
usage: emacspro -h    --  show help
       emacspro -d    --  show profiles directory
       emacspro -l    --  list profiles
       emacspro [...] --  open files in emacs using profile set in EMACS_PROFILE env var
                          if EMACS_PROFILE env var not set, defaults to 'default'
```

To add a new profile, create a new directory in the `~/.local/share/emacspro/profiles`
directory with the contents of what would typically go in your `~/.emacs.d` directory.

If you have an existing `~/.emacs.d` directory, you can simply symlink it to a new
directory in the `~/.local/share/emacspro/profiles` directory.

If you use a profile that hasn't been created yet, `emacspro` will create its
profile directory for you in the `~/.local/share/emacspro/profiles` directory.

To remove a profile, simply delete its directory.
