# Load an SSH key for the day using LastPass CLI

At [Pivotal](https://pivotal.io) we share Mac workstations, so we typically log in for the day.

I used to carry my SSH key on a USB stick. Now it's a backup and I load my SSH key using LastPass.

## Prerequisites

1. [LastPass](https://lastpass.com/) account
1. LastPass CLI: `brew install lastpass-cli`

## Set up

1. Create a new SSH key; GitHub has a [decent guide](https://help.github.com/articles/generating-an-ssh-key/)

1. Put the private key in the notes field of a LastPass secure note, e.g. "Personal/GitHub SSH key"

1. Customise the [load script](https://github.com/jamesjoshuahill/lastpass-ssh-key/blob/master/load), with your own variables

1. Put your custom load script in the notes field of another LastPass secure note, e.g. "Personal/Load GitHub SSH Key"

## Usage

```bash
lpass login $USERNAME

# Load your SSH key until hometime!
bash <(lpass show 'Personal/Load GitHub SSH Key' --notes)

# Or, load your SSH key for 2 hours!
bash <(lpass show 'Personal/Load GitHub SSH Key' --notes) 2
```
