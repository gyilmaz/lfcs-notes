
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
* 
