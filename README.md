# systemd-cleanup-pacman-hook

Stop and disable systemd units before removing packages

### Installation

`$ aur_helper -S systemd-cleanup-pacman-hook`

### Usage

Just remove packages as usual using `pacman`, and it will be taken care of automatically for you.

#### Revert changes to units

The provided hook doesn't remove the override files (e.g. drop-in files) for the unit.

To also remove those automatically, modify the hook to use `--revert` option:

```console
# install -Dm644 /usr/share/libalpm/hooks/systemd-cleanup.hook /etc/pacman.d/hooks/systemd-cleanup.hook
# sed -i '/^Exec =/s/$/ --revert/' /etc/pacman.d/hooks/systemd-cleanup.hook
```

#### Check for broken symlinks

There might have already been broken symlinks to deleted systemd units in your system (before installing this hook).

You can use the command below to check for them:

`# find /etc/systemd/{system,user} -xtype l`
