You can put your flags in a `chromium-flags.conf` file under `$HOME/.config/` (or under `$XDG_CONFIG_HOME` if you have configured that environment variable) or `/etc/` for global.

No special syntax is used; flags are defined as if they were written in a terminal.

- The arguments are split on whitespace and shell quoting rules apply, but no further parsing is performed.
- In case of improper quoting anywhere in the file, a fatal error is raised.
- Flags can be placed in separate lines for readability, but this is not required.
- Lines starting with a hash symbol (#) are skipped. (This is only supported by the Chromium launcher script and will not work when using Google Chrome.)

Below is an example `chromium-flags.conf` file that defines the flags `--start-maximized --incognito`:

`~/.config/chromium-flags.conf`
```
# This line will be ignored.
--start-maximized
--incognito
```