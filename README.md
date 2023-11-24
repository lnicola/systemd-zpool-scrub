# zpool-scrub
systemd zpool scrub service and timer

## Installation

### Arch Linux
You can use the `systemd-zpool-scrub` AUR package.

### Linux
    install -m 644 -o root -g root zpool-scrub@.service /etc/systemd/system
    install -m 644 -o root -g root zpool-scrub@.timer /etc/systemd/system

    systemctl daemon-reload
    # enable for `tank`
    systemctl enable --now zpool-scrub@tank.timer

    # enable for every pool
    for p in $(zpool list -H | cut -f1); do systemctl enable --now zpool-scrub@$p.timer; done
