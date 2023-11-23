# zpool-scrub
systemd zpool scrub service and timer

## Installation

### Arch Linux
You can use the `systemd-zpool-scrub` AUR package.

### Linux
    install -m 644 -o root -g root zpool-scrub@.service /etc/systemd/system
    install -m 644 -o root -g root zpool-scrub@.timer /etc/systemd/system

    systemctl daemon-reload
    for i in $(zpool list |grep -v NAME | awk '{print $1}') ; do systemctl enable --now zpool-scrub@$i.timer; done
