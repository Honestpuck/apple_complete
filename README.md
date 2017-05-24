## bash completion for Apple tools

These are a number of scripts designed to add programmable completion to
`bash` for some of the command line tools. They complete the options for
each tool, for most the completion cuts in after `-` or `--`.

If you have installed bash completion using `brew` then drop the files
into `/usr/local/etc/bash_completion.d/` (or link them) and open a new
Terminal window.

Feedback, bug reports and comments would be greatly appreciated. If you
want to nominate a CLI tool for me to add to this set, drop me a note or
open an issue.

### Notes

#### bless

For `bless` it first completes on the action option and then
completes on the options for that action.

#### diskutil

For `diskutil` it first completes on the verb and then the options for
the verb. For options prefaced with `-` it will only complete after you
enter the `-`. For verbs such as `eraseDisk` where you specify a format
argument it will also complete the formats. No work has been done to
create more specific completion than at the verb level or to make sure
you have options and arguments in the right order.

 