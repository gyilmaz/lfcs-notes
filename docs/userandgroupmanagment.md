
## Managing users/groups 
* `sudo usermod -e 2030-03-01 jane` : setting the expression date
* `sudo useradd --system apachedev` : create a system account 
* `sudo usermod -e "" jane` : setting unexpired user
* `sudo useradd -s /bin/csh jack` : setting user with default home dir
* `sudo userdel -r jack` : deleting user with home folder
* `sudo chage --lastday 0 jane` : force user password to expire to immediately change on next login
* `sudo usermod -a -G developers jane` : add user to group called developers
* `sudo groupadd -g 9875 cricket` : crete a group and set the id
* `sudo groupmod -n soccer cricket` : rename a group called cricket
* `sudo useradd -G soccer sam  --uid 5322` : create a user with user id and add it to a group 
* `sudo usermod -g rugby sam` : update primary test
* `sudo usermod -L sam` : Lock the user
* `sudo groupdel appdevs` : delete the group
* `sudo chage -W 2 jane` : user gets password warning  2 days before pass expire


## Manage Users Env
* ` /etc/environment` : used to set the globally available environment variables in a Linux based system.
* `env` : print environemnt 
* `vi ~/.bashrc` : to add change env variables and add `export MYVAR=TRUE` then save and run `source ~/.bashrc`
* `sudo cp /etc/skel/.bash* /home/bob/default_data/` user data
* `/etc/profile.d/welcome.sh` : user messages when login
* `sudo touch /etc/skel/README` : Whenever we create a new user in Linux the files in /etc/skel directory get copied into the user's home
* `vi /home/bob/.bashrc` : open the config and  Update the user path variable `PATH="$HOME/.local/bin:$HOME/bin:$HOME/.config/bin:$PATH"`

###

*`sudo vim /etc/security/limits.conf` : to see domain,type,item limit values "*" will set default for all users 
hard and soft limits are defined.  

### Manage User Resources
*`sudo gpasswd -a trinity wheel` : allow user to use sudo commands
* `sudo vi /etc/security/limits.conf` and add `trinity - nproc 30` : to limit user to run 30 process max
* `ulimit -a` : print out all limits of the current user
* `sudo visudo /etc/sudoers`  and add `trinity    ALL=(ALL)   NOPASSWD: ALL` : allow user to run all sudo commands without password required
* `sudo visudo /etc/sudoers`  and add `trinity ALL=(ALL) /usr/bin/mount` : only execute with bin mount
* `sudo vi /etc/security/limits.conf` and add `stephen hard fsize 4096` : allow only to create 4MB file
* `sudo vi /etc/security/limits.conf` and add `@salesteam     soft    nproc     20` : set a set limit on group
* `sudo visudo /etc/sudoers`  and add  `%salesteam     ALL=(ALL)     ALL` : sales team can run sudo command
* `sudo visudo /etc/sudoers`  and add  `trinity   ALL=(sam)   ALL` : trinity can run command as sam
* `sudo visudo /etc/sudoers` and add  `@developers     hard    nproc  10` : hard limit to 10 for developer group
* `sudo visudo /etc/sudoers` and add `trinity ALL=(ALL) ALL` : password required for trinity to run sudo
