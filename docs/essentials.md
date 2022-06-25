# Useful Command

## SSH:

* `ssh`
* `ssh --help` : show help
* `ssh <username>@<hostname>` : define username & hostname
* `ssh -v` : verbose

## Hostname

* `hostnamectl`
* `hostnamectl set-hostname <name>` : set hostname

## Directories & File Management

* Show directory
  * `ls -la` : show details & hidden files
  * `ls --full-time` : show full time of files/dirs
* `touch <filename>` : create empty file
* `pwd` : show current directory
* `cd <location>` : change directory
* Make Directory
  * `mkdir <dirname>` : make empty directory
  * `mkdir -p <dir>/<dir>/<dirname>` : create the parent if not exist
* Copy
  * `cp <sourcefile> <destfile>` : copy file
  * `cp -r <sourcedir> <destdir>` : copy directory
  * `cp -a <sourcefile> <destdir>` : copy file (preserve file attributes)
* Delete
  * `rm <filename>` : remove file (can be used to empty directory)
  * `rm -rf <dirname>` : remove directory, sub dir, and all files inside dirname
* Move
  * `mv <olddir>/* <newdir>` : move contents from old dir to new dir
  * `mv <oldlocation> <newlocation>` : move file (can be used as rename)
* Linking File
  * `ln <file> <file>` : hard link
  * `ln -s <dir/file> <dir/file>` : soft link
* Search Files
  * `find <dir> --mmin -<minute>` : find last modified in the last n minutes
  * `find <dir> -perm -g=w ! -perm /o=rw` : (-) at least, (/) or, (!) negation
  * `find <dir> -size <>k -o -perm 402` : find by size & octal permission
  * `find <dir> -name <filename>` : find by filename/dirname
  * `find <dir> -type d -name <dirname>` : find directory by name (change to f if want file)
  * `find <dir> -type f -size +<low> -<high>` : find files with size between low and high
* Permissions
  * `chmod g-<permission> <file>` : Remove permission from group
  * `chmod 0755 <file/dir>` : Change mode to `rwxr-xr-x`
  * `chmod u+s,g+s,o+t <dir>` : setuid, setgid, sticky bit
* Update File Content
  * `sed`
  * `sed -i 's/<from>/<to>/g' <file>` : change all values of `<from>` to `<to>`
  * `sed -i 's/<from>/<to>/gi' <file>` : change all values of `<from>` to `<to>` (ignore case)
  * `sed -i '100,500s/<from>/<to>/gi' <file>` : change all values of `<from>` to `<to>` from line `100` to `500`
  * `sed -i 's~<from>~<to>~g' <file>`: with special character
* Show File Content
  * `head -<n> file` : show top of n lines
  * `tail -<n> file` : show bottom of n lines
  * `grep` : Filter output by pattern
  * `grep -c '<patter>' <filename>` : count the matched pattern (combined with `i` for ignore case)
  * `grep -w '<pattern>' <filename>` : grep with matched pattern and match whole word
  * `egrep -w '<pattern>' file` : grep each lines with pattern and match whole word
  * `cut -d ';' -f <column> <file>` : split each lines with delimiter `;` and take a column
* Show Diff
  * `diff -i <file1> <file2>` : show diff with ignore case

## Manual

* `apropos <command>` : get detail of related commands
* `mandb` : correction to manual docs

## Sections

* Section 8: System administration commands

## Shortcut/Keyboard Tips

* `...` + TAB + TAB : show suggestion command

## Archive

* `tar cfP <destination>.tar <source>` : `f` (define filename), `c` (create archive), `P` (absulute names)
* `tar czfP <destination>.tar.gz <source>` : `z` (gzip)
* `tar tfP <file>` : `t` (list)
* `tar xf <file> -C <dir>` : `x` (extract), `C` (define directory)
* `bzip2 --keep <file>` : bzip file and keep the orginal file
* `gzip <filename>` : gzip `filename`
* `unxz <filename>.xz` : unxz file

## Output

* `<script> > <output>` : (stdout only)
* `<script> > <output> 2>&1` : stdout & stderr (err & warning) (`2>&1`)
* `<script> 2> <output>` : stderr
* `<script> >> <output>` : append output

## Sort

* `sort -duf <file>` : sort output, `d` (dictionary sort), `u` (unique), `f` (ignore case)
