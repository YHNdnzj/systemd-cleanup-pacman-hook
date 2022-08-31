# systemd-cleanup-pacman-hook

Stop and disable systemd units before removing packages

### Installation

`$ aur_helper -S systemd-cleanup-pacman-hook`

### Usage

Just remove packages like usual using `pacman`, and it will be taken care of automatically for you.

#### Check for broken symlinks

There might have already been broken symlinks to deleted systemd units in your system (before installing this hook).

You can use the command below to check for them:

`# find /etc/systemd/{system,user} -xtype l`
