# zpool-scrub
systemd zpool scrub service and timer

## Installation
    install -m 644 -o root -g root zpool-scrub@.service /etc/systemd/system
    install -m 644 -o root -g root zpool-scrub@.timer /etc/systemd/system

    systemctl daemon-reload
    systemctl enable zpool-scrub@tank.timer
    systemctl start zpool-scrub@tank.timer
