## DERFINE DIRECTORY
| command       | description           |
| ------------- |:-------------:|
| .             | current directory|
| ..            | parent directory      |
| cd            | change to the home directory    |

## HOW FIND FOLDER BY NAME
starts with the current directory (no need to specify directory in case of current directory)

```
find -name "*c*" -type d
```
| parameter     | description           |
| ------------- |:-------------:|
| -name "*c*"   | with name contains the letter c|
| -type d       | which are a directory     |
| -iname        | like name but ignores case   |

### More examples
You can run the command on other directory (/full/path/to/dir) using:
```
find /full/path/to/dir -name "*c*" -type d
```
Find in folder projects all files, which name is README
```
find projects -name README
```
Find files, that are more than 13 < days old < 10
```
find . -mtime +10 -mtime -13
```
Find files, that are more than 13 < days old < 10 and use ls for the result
```
find . -mtime +10 -mtime -13 -ls
```
Find only files by name
```
find /path/to/search -name filename -type f
```
Find executable files
```
find /path/to/search -type f -executable
```
Counting how many things you find
```
find /path/to/search | wc -l 
```
Find only directories with name AK without any files inside
```
find AK -maxdepth 1 -type d.
```
Find file in all machine
```
find / -name "filename" 
```						
## man
| command       | description           |
| ------------- |:-------------:|
| space         | to go on the next page|
| g             | go to the begining og man     |
| G             | go to the bottom of man   |

if you don't know exactly command, which you're looking for
```
man -k <searchTeem>
```

## ls
| command| description           |
| -------|:-------------:|
| -a     | show all folders, which begin with . (means the are hidden files)
| -l     | show long information about file     |
| -F     | show you type of file /=folder. @=link *=executable  |
| -r     | reverse the order
| -t     | sort by the time    |
| ``<folder> ``    | execute ls in folder    |


## which <command>
command show you, where command is located 
```
which cat
```

## mkdir
create directory with children, if need. for exmaple 1/2/3
```
mkdir -p 
```

## Delete file
delete folder and all files in it
```
rm -rf <folder>
```
| parameter       | description           |
| ------------- |:-------------:|
| -r         | remove content|
| -f             | without prompt for comfirmation    |

## Copy file 
Copy file1, file2, etc. to destination directory
```
cp src_file1  [src_fileN...]   dest_dir
```
if folder not exists, create a folder (when copy folders)
```
cp -r 											
```

## mv =move or rename files and direcories
| command       | description           |
| ------------- |:-------------:|
| mv dir firstdir  | ename dir to firstdir|
| mv file1.text firstdir| remove file1.txtx in firstdir |
| mv file1 file2 | if file2 exists, it will overwrite file2 of the content of file1 |
|mv -i |it will ask, do you want to rename it or not|

## tree 
show the tree of folders
show the color of different types of files = folders, executable, etc.
```
tree -C 
```

## chmod 
all users are allowed only to read file
```
chmod a=r
```

## umask
make special permissions by default for the folder and files in it


## DISPLAYING THE CONTENTS OF FILE

### cat file
display the contents of file - convinient for short files

show file with numbers
```
cat -n <file> 
```

### more file 
browse through a text file - it works more quicker than less.

### less file 
more features than more

### head file
output the begining (or top) portion of file

show 15 lines of file (by default it's 10 lines)
```
head -15 file.txt
```
### tail file
output the ending (or bottom) portion of file
```
tail -15 file.txt
```
show 15 lines of file (by default it's 10 lines)
```
tail -f file
```
displays the data as it's being written to the file

### sort text in file
| command| description    |
| -------|:-------------:|
|sort `<nameOfFile>`|sort text in alphabetical order|
|sort -u `<nameOfFile>`| sort text in alphabetical order and show only unique lines
|sort -r `<nameOfFile>`| sort text in alphabetical order and reverse order

### nano
| command| description    |
| -------|:-------------:|
|ctrl+X| exit from editor
|ctrl+G| help of nano

### grep
| parameter| description    |
| -------|:-------------:|
|-i  | Perform a search,ignoring case
|-c  | Count the number of occurences in a file
|-n  | Precede output with line numbers
|-v  | Invert Match. Print lines that don't match

*Example*

cat logs, where there is word "error"  
```
cat Robustness.log | grep "error"
```
#### More Exmaples
show the count of word error in file, ignore the case
```
grep -ci error setup.log
```

find word "we" and replace it to "akozyreva"

```
grep "we" -ir -H ./prodigy.txt
grep "we" -rl -H ./prodigy.txt | xargs sed -i "" 's/We/akozyreva/g'
```

## vim
### READ MODE
how move the cursor in vim	
```
	^
	k
<h 		l>
	j
```

how move cursor in line

| parameter| description    |
| -------|:-------------:|
|^|move to the begining of line
|$ |go to the end of line

how move between words

| parameter| description    |
| -------|:-------------:|
|w |right one word
|e  |from left to right to the next word
|2w	|right on the 2 words
|b 	|left one word

### EDIT
| parameter| description    |
| -------|:-------------:|
|x |			remove the caracter under the cursor
|dw |			delete a word
|d2w	|		delete 2 words
|dd |			delete a line 
|D |			delete from the current position
|I |			insert in the beginning of line

### APPENDING=append after line
| parameter| description    |
| -------|:-------------:|
|a|			Append text after the cursor [count] times.
|A|			Append text at the end of the line [count] times.
|:x |			same as wq
|:n |			position of the cursor on the line n
|:$ |			position of the cursor on the last line
|:set nu | 	turn on numbering
|:set nonu |	turn off numbering

### CHANGING TEXT
| parameter| description    |
| -------|:-------------:|
|r`<charachter>`| 		replace the current character
|R`<characnters>`| 		replace more than one character
|cw|		change the current word
|cc |		change the current line
|c$	|	change the text from the current position to the end of line!
|C |		same as c$
|~|		reverse the case of character

### COPY-PAST
| parameter| description    |
| -------|:-------------:|
|yw| 		copy one word
|yy	|	yank copy the current line
|y`<position>`|	copy the position
|p| 		past the most recent deleted or yanked text

### STEP FORWARD/PREVIOUS
| parameter| description    |
| -------|:-------------:|
|u |		step previous
|U| 		return all the line to it's original state
|cltr+R |	next step

### SEARCHING
| parameter| description    |
| -------|:-------------:|
|`/<pattern>`|start a forward search
|`?<pattern>`	|start a reverse search
|ctrl+O| 		go back to where you came from
|% |find the ending of parentheses
|`:s/<oldWord>/<newWord>/g`| change oldword to new in all line 	
|`:s/<oldWord>/<newWord>/`| change oldword to new in 1 occurence
|:%s/`<oldWord>/<newWord>/`g |  	change every occurence in the whole file
|:%s/`<oldWord>/<newWord>/`gc |  	change every occurence in the whole file with a prompt 									whether delete it or not

### CURSOR LOCATION
| parameter| description    |
| -------|:-------------:|
|ctrl+G| 						show location in the file and the file status
|`<numberOfLine>`G |			go on the line
|G| 							go to the bottom of file
|gg|  						move to the start of the file

### EXECUTION
this allow you to execute external commands

```:!<name of command>```


### CREATION OF FILE
create a new file

```:w <name_of_new_file>```


## VISUAL MODE
```v = visual mode```

## COPY AND PASTE IN NEW FILE
1. Move the cursor to this line.
2. Press  v  and move the cursor to the fifth item below.  Notice that the
     text is highlighted.
3. Press the  :  character.  At the bottom of the screen  :'<,'> will appear.
4. Type  w TEST  , where TEST is a filename that does not exist yet.  Verify
     that you see  :'<,'>w TEST  before you press <ENTER>.
5. Vim will write the selected lines to the file TEST.  Use  :!dir  or  :!ls
     to see it.  Do not remove it yet!  We will use it in the next lesson.


## RETIEVE VALUE FROM FILE
| parameter| description    |
| -------|:-------------:|
|r:`<name of file>` |insert the text from old file to new file
|r: !ls | 			reads the output of the ls command and puts it below the cursor 

### view file 

vim but in only-read mode

| parameter| description    |
| -------|:-------------:|
|o| 					open up a line below the cursor and place you in Insert mode
|O|  					open up a line above the cursor and place you in Insert mode


### ARCHIEVE
```tar```

| parameter| description    |
| -------|:-------------:|
|c| 			create archive
|x| 			extract files from the archive
|t| 			display the table of contents (list)
|v |			be verbose (view files, which were extracted)
|z|  			use compression
|f file| 		use this file

#### Examples
create archive
```     
tar cf tars.tar Robustness.log
tar zcf tars.tgz Robustness.log
```
extract archive
```
tar xf tars.tar
```
show files in archive
```
tar tf tars.tar
```
create archive from folder
```
tar -zcvf archive-name.tar.gz directory-name
tar czf tars.tar ./.test
```
### Compressing files
| command| description    |
| -------|:-------------:|
|gzip|  		compress files
|gunzip|  	uncompress files
|gzcat|   	concatenates compressed files
|zcat |  		concatenates compressed files


### Disk Usage
| command| description    |
| -------|:-------------:|
|du| 		Estimate file usage
|du -k |	Display sizes in Kilobytes
|du -h | 	Display sizes in human readable format


### About keys on Mac
The “Home” button on a Macbook Pro keyboard: Fn + Left Arrow.
The “End” button on a Macbook Pro keyboard: Fn + Right Arrow.

### Wildcards

|parameter| description    |
| -------|:-------------:|
|* |matches zero or more characters
|? | matches exactly one  character
|??| matches 2 characters
|/ |escape character
|*.txt| matches all files with txt extension
|a?.txt |find a and one character.txt - for exmaple as.txt
|mv *.txt notes  |move all files with extension txt to folder notes
|mv *.txt| delete all files with txt extension

## Redirection

|parameter| description    |
| -------|:-------------:|
|> |redirect output to file 
|>> |redirect standard output to a file(appends to any existing contents) 
|<  | redirect input from a file to a command
|>/dev/null |redirect output to nowhere

*Examples*

```
ls a*.txt > /dev/null
```

sort all output from fil aa.txt

```
sort < aa.txt
```

sort files from the files.txt and input the result in sorted_files.txt

```
sort < files.txt > sorted_files.txt
```

## Comparing files
|command| description    |
| -------|:-------------:|
|diff file1 file2 |  	Compare two files
|sdiff file1 file2 |  Side-by-side comparison
|vimdiff file1 file2 |    Highlight differencies in vim


### File 
Display the file type

```
file sales.data
```

### cut 
Useful documentation 

https://ss64.com/bash/cut.html

it only cut the output, not the file itself

show the first field of the line, separating by comma

```
cut -d':' -f1 /etc/passwd
```
https://www.thegeekstuff.com/2013/06/cut-command-examples

### alias
Command for creating shrotcut of command.

For example in order not to type ls-l all the time you can create alias of it and type only ll

### unalias
command for delete aliases

### printenv
see all env_variables in your system

*Examples*
```
printenv HOME
```
see the value of env_variable of HOME or 
```
echo $HOME
```
for creating variable
```
export VAR="value"
```
but it should work only for terminal session
```unset VAR
```
for deleting variable

to add constantly variable you need to add it in ~/.bash_profile

### Processes and Job Control
|command| description    |
| -------|:-------------:|
|ps|     Display process status (without options - only processes in current session)
|ps -e |   everything, all processes
|ps -eH  |  display all processes, full
|ps -e --forest  |  display a processes tree
|ps -f |   full format listing
|ps -u username |   display usernames's processes
|ps -p pid    |     display information for PID (process id, which can be found in ps command)
|pstree|     display processes in a tree format
|top     |   interactive process viewer
|htop |      the same viewer but look cooler
|command & |   start command in background
|Ctrl-c   |    kill the foreground process
|Ctrl-z |      suspend the foreground process
| kill     |    kill a process by job number or PID


### Cron
cron  runs sheduled jobs, for exmaple - run every Monday at 07:00
```
0 7 * * 1 /opt/weekly-report
```
|command| description    |
| -------|:-------------:|
|crontab file |   install a new crontab from file
|crontab -l   |   List your cron jobs
|crontab -e |     Edit your cron jobs
|crontab -r   |   Remove all of your cron jobs

### User
su    change user. by default it means superuser
su - oracle    change user on oracle

### sudo 
Allows you to execute command as another user, typically the superuser

run command as root
```
sudo command     
```
Run as user1
```
sudo -u user1 command    
```
return account name
```
whoami
```    

### yum
yum allows to install packages from open Internet (firefox, for exmaple)
|command| description    |
| -------|:-------------:|
|yum search string|        search for string
|yum info [package] |      display info
|yum install -y package| install without saying yes
|yum remove package  |      remove package

### rpm
rpm has the same functionality as yum but it installs packages, which are local stayed
List all installed packages
```
rpm -qa      
```

### nohup
nohup uses for running processes in background - returns id of process
```
nohup ./start_test.sh &
```

## TMUX (ITerm2 + Mac)
Assuming the default tmux configuration is being used, novice tmux users please follow the instructions below to split the pane

*To split the pane horizontally*

 - Press Ctrl+B
- Release pressed keys in Step 1
- Press "  (on many keyboards, this is Shift+')

*To split the pane vertically*

- Press Ctrl+B
- Release pressed keys in Step 1
- Press %  (on many keyboards, this is Shift+5)

To close a single pane in tmux, you need to either press Ctrl+d or type exit and press Return.

## git
discard local changes in git

```
git clean -df
git checkout -- .
```

## disk and memory
|command| description    |
| -------|:-------------:|
|lvmdiskscan   | show all disks on computer
|lsblk         |show all disks but in tree structure
|lsblk -p |      show all disks with tree structure and full path
|df -h      |    show all disks and their size
|vgs|            list all VLM groups
|lvdisplay |     list all lv_logical_layers
|free -h |    show memory (ozu/RAM)

### Docker
|command| description    |
| -------|:-------------:|
|docker image ls  |  look all images, which you have
|docker ps -a     |show all containers
|docker info|     info about docker
|docker build -t dockerize-vuejs-app .     |  build container
|docker rmi $(docker images -q).  | delete all images
|docker container ls |

for running docker container
```
docker run -p 80:80 akozyreva/docker-tutorial:part2
```

 ip adress
 cent os 
 ip a     show ip address
 Explanation of output
 lo      show addres, which uses Linux by itslef for communication
 eth0    harware device
 on mac 
 ifconfig

add public key to authorized keys
echo public_key_string >> ~/.ssh/authorized_keys
cat id_rsa.pub >> ~/.ssh/authorized_keys

ping HOST    send packages to the host in order to ckeck whether there is connection or not
ping -c COUNT HOST    send certain amount of packages
ping -c 3 google.com

examine route (more detailed, than ping)
traceroute -n google.com

another command for checking network
tracepath -n google.com


look whether packets sends or not
tcpdump 
-n    Display numerical addresses and ports
-A    Display ASCII text output
-v    Verbose mode. Produce more output

telnet can be used for checking network (in example bellow checks wheter connection is accepted to 80 port - http - or not)
telnet google.com 80    