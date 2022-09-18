# Useful Command (Centos & Ubuntu)

## Booting

* `/etc/default/grub` : grub configuration file, (default timeout)
* `grub2-mkconfig -o /boot/grub2/grub.cfg` : generate new grub config file, (Ubuntu use `grub-mkconfig`)
* `grub2-install <device target>` : install grub2 to target (Ubuntu use `grub-install`)
* `systemctl set-default graphical.target` : change graphical desktop by default
* `systemctl get-default` : get default

## Shutdown

* `shutdown +n` : shutdown after `n` minutes
* `shutdown -c` : cancel shutdown

## Services

* `systemctl enable rpcbind.service` : enable `rpcbind.service` at startup
* `systemctl status sshd.service` : check `sshd.service` status
* `systemctl is-enabled sshd.service` : check `sshd.service` is enabled
* `systemctl mask httpd.service` : mask `httpd.service` (strong version of disable)
* `systemctl daemon-reload`
* `journalctl --unit=sshd.service -n 20 --no-pager` : show service logs
* `journalctl -p err` : show error logs with priority flag
* `journalctl -p info -g '<pattern>'` : show info logs and pattern

## Processes

* `ps lax` : all processes running & nice values
* `ps u <pid>` : show process by pid
* `sleep n` : halt main process n seconds
* `<command> &` : run in background
* `jobs` to see running process in a background
* `bg <id>` to run the command to run in background 
* `renice <new value> <pid>` : set new nice value
* `nice -n <value> <name>` : set process `<name>` with nice `value`
* `lsof -p <pid>` : list all files opened by pid
* `pgrep -a <pattern>` : process grep, `a` get all
* `fg` bring to app in a foreground to continue to process

## Logs
* `ls /var/logs` root user can see the system log files
* `which sudo` then  `journalctl /bin/sudo/` instead of taling or using grep
* `journalctl -p` <tab> <tab>

### Signal

* `kill -<signal> <pid>` : kill pid with signal
  * `SIGHUP` : hang up

### Cron

* `crontab -l` : show cron list
* `/var/log/cron` : cron logs
* `anacron -n -f` : force anacron
* `atq` : find jobs
* `atrm <job number>` : remove job
* `sudo crontab -e` : edit cron config, format: `<time> <command> <others>`

## Scripts

* `#!` : `shebang`
