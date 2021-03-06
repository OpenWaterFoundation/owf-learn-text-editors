# Text Editors / vim

* [Overview](#overview)
* [Resources](#resources)
* [Use](#use)
* [Configuration](#configuration)
* [Emulation in Software](#emulation-in-software)
* [Troubleshooting](#troubleshooting)

--------------------------

## Overview

The free and open source `vim` editor provides both a command-line editor (`vim`) and graphical user interface editor (`gvim`).
The `vim` editor is often distributed by default with Linux-like operating systems such
as Git Bash and provides a way to edit files on remote systems when a graphical user interface cannot be run.
`vim` can be very efficient to use for users who are adept at typing by touch given the minimal use of `Ctrl`, `Alt`, etc.

On Cygwin, the graphical user interface can be started only after setting the `DISPLAY` environment variable to
a proper value and running the X Windows Server:

1. Start X Windows using ***Start / Cygwin-X / XWin Server***.
2. `export DISPLAY=:0.0`

## Resources

* [vim home page](https://www.vim.org/download.php)
* [vim man page](http://linuxcommand.org/lc3_man_pages/vim1.html)
* [vim tutorial](https://www.openvim.com/)
* [vim cheat sheet](https://vim.rtorr.com/) - there are many on the web

## Use

The `vim` editor uses two modes to edit files:

1. Command mode
2. Insert mode

When in insert mode, characters that are typed result in text being inserted in the file.
When in command mode, characters that are typed, result in actions such as moving the cursor,
deleted characters, searching, etc.
To move from insert mode to command mode, use the `ESC` (escape) key.
When in insert mode, `vim` will typically show `INSERT` in the bottom of the window.

The following are useful examples:

* To see end of line characters, edit a file using binary mode:  `vim -b filename`.
In particular, Windows carriage return will be shown as `^M`.
It is recommended to not save text files with binary mode - just use for confirmation
of end of line or to see other binary content.

## Configuration

The `vim` editor is configured at runtime using the set command.
For example, the following sets ignore case when searching:

```
:set ic
```

To ensure that such configuration is in effect each time that `vim` is started,
configuration settings can be added to a `.vimrc` file in the user's home folder.
[See the example `.vimrc` configuration file](vimrc.txt) for useful configuration settings..

## Emulation in Software ##

vim emulators that mimic vim behavior are available in software tools, including:

* [Atom Editor](../atom/atom.md)
* [Eclipse IDE](https://www.eclipse.org/ide/)
	+ use [VRapper](http://vrapper.sourceforge.net/home/) or newer options
* [Visual Studio Code](../vs-code/vs-code.md)

## Troubleshooting ##

The following are some common issues.

| **Issue** | **Possible Solution** |
| -- | -- |
| Keyboard freezes in vim session. | This can occur if `Ctrl-s` was accidentally entered.  Use `Ctrl-q` to return to normal mode. |
| Pasting content from Windows command prompt window or other source causes control characters to show and cannot edit normally. | [This is an open issue](https://github.com/OpenWaterFoundation/owf-learn-text-editors/issues/2) for this documentation. |
