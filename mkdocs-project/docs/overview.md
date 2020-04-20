# Text Editors / Overview

Text editor software is used to edit text files on a computer.
Text editors are used to edit data files, write software code, edit documentation, etc.
Any person that is working text files needs to use a text editor
that results in maximum efficiency.
A good text editor and multiple computer displays (or one big display) can
be the most useful tools for a software developer.

* [General Considerations](#general-considerations)
	+ [Operating System](#operating-system)
	+ [Remote Access](#remote-access)
	+ [End of Line](#end-of-line)
* Editors (links to other pages)
	+ [Atom (from GitHub)](atom/atom.md)
	+ [Notepad (from Windows)](notepad/notepad.md)
	+ [`notepad++`](notepad-plusplus/notepad-plusplus.md)
	+ [Sublime](sublime/sublime.md)
	+ [Textpad](textpad/textpad.md)
	+ [UltraEdit](ultraedit/ultraedit.md)
	+ [`vim`](vim/vim.md)

--------------------------

## General Considerations ##

Text editors are generally comparable for basic features.
The following are important considerations:

1. Does the editor automatically detect line ending character (Windows or Linux) and use that
convention when adding new lines.
Most editors handle this and may show an indicator for the line ending type.
It is important that a file, when saved, has consistent line endings
so as to not confuse editors, compilers, Git, and other tools.
2. Does the editor use tabs or spaces for indentation?
Ideally it can be configured to display tabs.
Spaces should be used in code if possible because tab spacing may vary between developers and tools.
Otherwise, formatting issues may arise.
3. Some editors create temporary and backup files.
These files need to be ignored using Git `.gitignore` file so as to not commit to the repository.
4. Many editors include spell checkers.
Avoiding typos and misspelled words in code is desirable.
5. Does the editor auto-detect different software language and provide useful features?
For example, context-sensitive help and code navigation can be helpful.

The following sections provide more extensive discussion of various considerations.

### Operating System

Whether or not a text editor is available operating systems may be a major consideration.
Why learn and use multiple text editors on different operating systems?
The short answer is that it is generally best to choose and use the same tool on all operating systems.
However, this may not be possible given the limitations of the software.
It may also make sense to use different editors on different operating systems in order to better
represent the defaults on an operating system.
Users of a system should at least be exposed to default software on their system as an option
and not have to reproduce the perhaps highly customized environment of the software developer.

### Remote Access

It may be necessary to edit a file on a remote system.
In this case, there are generally three options:

1. **Command line editor** - Use an editor that runs in a terminal window using character input.
For example, the [`vim`](vim/vim.md) editor is available on most Linux-like systems
and can be run over `ssh` sessions in a terminal window.
For this reason, at least basic `vim` competence is desirable.
2. **Windowing environment** - Use an environment that allows graphical editors to be used.
On Linux this may mean using a tool like
[VNC](https://en.wikipedia.org/wiki/Virtual_Network_Computing) to share screens.
Or, use a virtual private network or remote desktop to gain access to the remote computer.
3. **Transfer the file** - lacking the ability to edit the file on the remote system,
it may be necessary to transfer the file to the local system, edit, and transfer back.
This is typically the least efficient but may make sense if local testing and archive of the file is needed.

More than one of the above approaches may be tried to find an efficient solution.

### End of Line

Text files use end of line characters to split the text file content into lines.
The end of line character is typically specific to the operating system as follows
(see also the [ASCII table](http://www.asciitable.com/)).

| **Operating System** | End of Line Long Name            | Escape Character | Notation         | ASCII Value |
| -------------------- | ---------------------------------|------------------|----------------- | ----------- |
| Linux                | Newline, also Linefeed           | `\n`             | `NL` or `LF`     | `10`        |
| Windows              | Carriage return + Newline        | `\r\n`           | `CRNL` or `CRLF` | `13` `10`   |

Most text editors will detect the end of line character being used and will
maintain the same character when new lines are inserted.
The end of line character(s) are typically detected from the first line in the file.
Editors will also typically indicate the end of line character in one way or another
to help understand the file format.
For example, the term `DOS` may be shown, indicating older DOS operating system,
which used the same end of line as Windows.
