# Store More Commands In Zsh History

__Category: Mac__

To increase the number of commands stored in the zsh history and log the time a command was run, edit `~/.zshrc` as follows:

```shell
export HISTSIZE=1000            # Store 1000 commands in history
export SAVEHIST=1000            # Save history after logout
export HISTFILE=~/.zsh_history  # History file
setopt EXTENDED_HISTORY         # Add timestamp for each entry
setopt INC_APPEND_HISTORY       # Append into history file
setopt HIST_IGNORE_ALL_DUPS     # Ignore duplicate commands
```

To enable this change, open a new shell or activate in the current shell with the following command:

```shell
source  ~/.zshrc
```

Commands will be stored in the ~/.zsh_history file with a Unix long timestamp. Any duplicate commands entered in succession will be de-duplicated.

To show history with timestamps in yyyy-mm-dd hh:ss format: 

```shell
history -i
```

To show the last 8 commands:

```shell
history -i -8
```
