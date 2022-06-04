# k1pwit: 1Password ❤️ iTerm2

k1pwit lets you to directly input passwords using [1Password](https://1password.com/) on [iTerm2](https://iterm2.com/), not via clipboard, just as though you do on Web browsers.
What k1pwit does is merely typing passwords for you; it just works with any shells, and notably with remote sessions over SSH.

![Screen Recording](https://user-images.githubusercontent.com/4177010/171969039-f855bb64-46cb-4cb1-8233-ac590b42a4d8.gif)

# Install

## Prerequisites

Before using k1pwit, you need to set up the following:

1. [iTerm2](https://iterm2.com/)
2. [op](https://1password.com/downloads/command-line/) (1Password CLI)
3. [jq](https://stedolan.github.io/jq/)
4. [fzf](https://github.com/junegunn/fzf)

If you use [Homebrew](https://brew.sh/), this is as easy as:

```sh
brew install iterm2 1password-cli jq fzf
```

## Setup

1. `git clone` (or download ZIP) this repository to wherever you want e.g. `~/k1pwit`.
2. Launch iTerm2, open _Preferences_ (<kbd>⌘ Comma</kbd>), and navigate to _Profiles_ > _Keys_ > _Key Mappings_.
3. Click `+` button at the bottom, and add a keyboard shortcut:
   - Keyboard Shortcut: (Whatever you like)
   - Action: _Run Coprocess_
   - Command: Full path to `launch` file in the k1pwit directory e.g. `~/k1pwit/launch`
4. Save it, close _Preferences_ and go back to shell.
5. Set up a config file by running `echo "PATH=$PATH" > ~/.k1pwitrc`.
6. If you haven't, initialize 1Password CLI configs by running `op account add`.

That's it!
Now try the keyboard shortcut you've just set up.
If everything is configured properly, a small pop-up window should appear.

# Configurations

You can put config files in any of the following locations:

- `${k1pwit directory}/.k1pwitrc`
- `~/.k1pwitrc`
- `~/.config/k1pwit/k1pwitrc`

For the available configuration options, you can find hints in [lib/load-config](./lib/load-config).

# Prior works

- https://github.com/yardnsm/tmux-1password
- https://github.com/ravenac95/sudolikeaboss
- https://github.com/geoffeg/opiterm which heavily inspired me on k1pwit's interface design

# License

k1pwit is licensed under [The MIT License](./LICENSE.txt).

© 2022 [Yusuke Kido](https://github.com/kissge).
