# Useful Command (Centos & Ubuntu)

## Booting

* `/etc/default/grub` : grub configuration file, (default timeout)
* `grub2-mkconfig -o /boot/grub2/grub.cfg` : generate new grub config file, (Ubuntu use `grub-mkconfig`)
* `grub2-install <device target>` : install grub2 to target (Ubuntu use `grub-install`)
* `systemctl set-default graphical.target` : change graphical desktop by default (Centos)
* `systemctl get-default` : get default (Centos)


## Shutdown

* `shutdown +n` : shutdown after `n` minutes
* `shutdown -c` : cancel shutdown
