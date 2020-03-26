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

### For zsh

You can use bash completions with `zsh` just close to the top of `.zshrc` put :
```
# bash compatible completion
autoload bashcompinit
bashcompinit
```

and the line `source <path to directory of completions>/*` right at the end, e.g. 
`source ~/bin/bash_completion/*`.

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
you have options and arguments in the right order. Quite a lot of the
verbs take no options.

#### hdiutil

For `hdiutil` it first completes on the verbs and then completes on the
options for each verb once you enter the `-`. No work has been done to
create more specific completion than at the verb level or to make sure
you have options and arguments in the right order.

#### quickpkg

It will complete all the options. If you enter the option `--ownership`
it will then complete on the the three possibilities. If you enter the
option `--keychain` then it will complete on all the keychains the 
system knows about.

#### networksetup

If you enter a `-` it will complete on the options (there are a heck of 
a lot). Most options require a service name, if you enter `"` then it
will complete on the current service names.

If you want to complete on a hardware port then enter `'` (that's a single
quote) then it will complete on the hardware ports. I'm still figuring out 
how to handle the few options that want *either* a hardware port or
device name.

The Airport and wireless options want a device name ('en0', 'bridge0' etc)
so they will complete the device names. This is handier on Macs with a 
bunch of psuedo devices.

More expansions to this may come. Feedback appreciated.
