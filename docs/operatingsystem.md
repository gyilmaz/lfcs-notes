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
* `journalctl -p info -g '^b'` to see info logs begin with b
* `journalctl -S 02:00` since option to set start time
* `journalctl -S 02:00 -U 02:30` until time also can be passed 
* `journalctl -b 0` this option displays current boot if journallogs to be saved `mkdir /var/logs/journal` can be created 
* `last` or `lastlog` to show who login  
 

### Signal

* `kill -<signal> <pid>` : kill pid with signal
* `SIGHUP` : hang up
 
###PowerTool

 * `sudo dnf config-manager --enable powertools`
 * `sudo dnf repolist --all`
 * `dnf group list` and `sudo dnf group install 'Container Management'`
 
 *` sudo dnf install nginx
    sudo dnf group list
    sudo dnf install 'Custom Operating System'
    sudo dnf group install 'Container Management'
    sudo dnf uninstall nginx
    sudo dnf --help
    sudo dnf remove ngnix
    sudo dnf remove nginx
    sudo dnf provides /bin/top
    dnf provides nginx
    dnf repoquery --list nginx | grep nginx-logo.png
    dnf repoquery --list nginx | grep nginx-logo.png >> /home/bob/nginx
    sudo dnf check-upgrade > upgrade.txt
    sudo dnf repolist -v > verbose.txt
    sudo dnf search "Apache HTTP Server" > webservers.txt
    history
    sudo dnf provides /etc/samba > forgot.txt
    sudo dnf repoquery --list curl > curl.txt`
 

### Get metrics
 
 * `df -h`
 * `free -h`
 * `uptime` : how much core cpus are used first1min, first5min,last30min
 * `systemctl list-dependencies`
 * `du -sh /bin/` to see storage
 * `lscpu` to see cpu cores per socket
 * `sudo xfs_repair /dev/vdb > /home/bob/fscheck 2>&1` /dev/vdb we have an XFS filesystem. Use the correct command to check this filesystem for errors and save the output in /home/bob/fscheck file.
 
 
 * Kernel runtime parameters 
  `sudo sysctl -a` : display parameters
  `sudo sysctl -w <parameter>=<0,or1> ` : to set parameter
  `sudo sysctl -p` : make it persistent
 
### Cron
 
* `cat /etc/crontab` to display example
* `crontab -l` : show cron list
* `/var/log/cron` : cron logs
* `anacron -n -f` : force anacron
* `anacron -T` : to test if syntax is correct
* `atq` : find jobs
* `atrm <job number>` : remove job
* `sudo crontab -e` : edit cron config, format: `<time> <command> <others>`
* `sudo crontab -r -u <username>` : remove crontab from a user
* Run the scritps hourly  create `touch shellscript` ,copy  `cp shellscript /etc/cron.hourly/shellscript`  and make executable `sudo chmod +rx /etc/cron.hourly/shellscript`
* `sudo cat /var/log/cron` to see what jobs run 
* to schedule a run using at for root `Switch to the root user using sudo -i command, then execute command at '15:30 August 20 2024'
Add /usr/bin/touch atscheduler line then save it by pressing CTRL+D `
 

## Scripts

* `#!` : `shebang`
 
 
 ## SELinux

* `ps axZ`
* `sudo semanage user -l` 
