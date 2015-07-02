# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges  

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
/home/cabox/workspace  

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
LICENSE    challenge_files        nix_scavenger_hunt_stretch.md            
README.md  nix_scavenger_hunt.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
There is a lot more detail included in this list. 
total 36K                                                                  
drwxrwxr-x 4 cabox cabox 4.0K Jul  1 12:12 .                               
drwxr-xr-x 9 cabox cabox 4.0K Jul  1 12:12 ..                              
drwxrwxr-x 8 cabox cabox 4.0K Jul  1 12:12 .git                            
-rw-rw-r-- 1 cabox cabox 1.1K Jul  1 12:12 LICENSE                         
-rw-rw-r-- 1 cabox cabox 1.4K Jul  1 12:12 README.md                       
drwxrwxr-x 7 cabox cabox 4.0K Jul  1 12:12 challenge_files                 
-rw-rw-r-- 1 cabox cabox 5.3K Jul  1 12:15 nix_scavenger_hunt.md           
-rw-rw-r-- 1 cabox cabox  317 Jul  1 12:12 nix_scavenger_hunt_stretch.md 

* The `man` ("manual") command tells you more about how any given command works. Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
I couldn't get man to run in shell. I recieved 'command not found' everytime I tried to use it. So I looked up what these commands do online. 
ls a - lists all files that start with . 
ls l - lists files in long format  
ls h - lists files in human readable font

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr              
boot  etc  home      lib64  mnt    proc  run   srv   tmp  var  

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/home/cabox   

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
using cd .. /home/cabox/workspace  

* Press the up arrow on your keyboard. *What just happened?*
pwd appeared at prompt

* Press the up arrow a few more times. *What do you see?*
cd ..
man
it is going backward to my last used commands

* Run the `history` command. *What do you see?*
history of my commands
   1  pwd                                                                 
    2  ls                                                                  
    3  ls -alh                                                             
    4  man                                                                 
    5  man man                                                             
    6  man ls                                                              
    7  ls man                                                              
    8  ls /                                                                
    9  cd /                                                                
   10  pwd                                                                 
   11  cd ~                                                                
   12  pwd                                                                 
   13  cd chellenge_files                                                  
   14  cd challenge_files                                                  
   15  whoami                                                              
   16  who                                                                 
   17  uptime                                                              
   18  ps aux                                                              
   19  top                                                                 
   20  cd challenge_files                                                  
   21  ls > files.txt                                                      
   22  more                                                                
   23  cd challenge_files                                                  
   24  pwd                                                                 
   25  ls                                                                  
   26  cd up                                                               
   27  man                                                                 
   28  cd ..                                                               
   29  pwd                                                                 
   30  man                                                                 
   31  history 

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox  

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
cabox    pts/1        Jul  1 17:37 (54.186.244.104) 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
17:59:15 up  5:47,  1 user,  load average: 0.00, 0.00, 0.00  

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
 17:59:15 up  5:47,  1 user,  load average: 0.00, 0.00, 0.00               
cabox@box-codeanywhere:~$ ps aux                                           
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND   
root         1  0.0  0.4  33208  2540 ?        Ss   12:12   0:00 init      
root         2  0.0  0.0      0     0 ?        S    12:12   0:00 [kthreadd/
root         3  0.0  0.0      0     0 ?        S    12:12   0:00 [khelper/4
root       160  0.0  0.1  19428   816 ?        S    12:12   0:00 upstart-ud
root       175  0.0  0.2  49216  1396 ?        Ss   12:12   0:00 /lib/syste
syslog     294  0.0  0.2 184188  1460 ?        Ssl  12:12   0:00 rsyslogd  
root       391  0.0  0.5  61316  3068 ?        Ss   12:12   0:00 /usr/sbin/
root       429  0.0  0.2  15768  1160 ?        S    12:12   0:00 upstart-so
root       435  0.0  0.1  15492   888 ?        S    12:12   0:00 upstart-fi
root       446  0.0  0.5  71260  2656 ?        Ss   12:12   0:00 /usr/sbin/
www-data   449  0.0  0.4 415720  2420 ?        Sl   12:12   0:02 /usr/sbin/
www-data   450  0.0  0.4 415720  2424 ?        Sl   12:12   0:03 /usr/sbin/
root       524  0.0  0.1  12740   844 tty1     Ss+  12:12   0:00 /sbin/gett
root       526  0.0  0.1  12740   856 tty2     Ss+  12:12   0:00 /sbin/gett
root       595  0.0  0.6  63876  3476 ?        Ss   17:37   0:00 sshd: cabo
cabox      597  0.0  0.2  63876  1464 ?        S    17:37   0:00 sshd: cabo
cabox      598  0.0  0.3  18128  2032 pts/1    Ss   17:37   0:00 -bash     
cabox      618  0.0  0.2  15520  1136 pts/1    R+   17:59   0:00 ps aux 
--Lists processes, statuses, and resource usage

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
Shows running stats                


### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
2
credit_cards.txt  credit_cards2.txt   

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
Last updated: 01-15-2015   

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
found between thses two tmp files
./tmp/qui_ab.txt                                                           
./tmp/modi_laboriosam.txt                                                  
./tmp/repellendus_iste.txt 

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
Britt-Erdman.user:O'Harachester, WA 37261                                  
Lissie-Strosin.user:Jewessfurt, WA 00816-7241  
count 2
grep -l 'WA' *.user 

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Wal
do sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectet
ur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia. 

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
a single column list of all the files in challenge_files 

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
A detail list of all the files in the directory, but with the option to pan down with space bar when ready.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
ot       623  0.0  0.6  63876  3480 ?        Ss   18:08   0:00 sshd: cabox [pri
v]                                                                               
cabox      625  0.0  0.2  64012  1484 ?        S    18:08   0:00 sshd: cabox@pts/
0                                                                                
cabox      626  0.0  0.3  18148  2072 pts/0    Ss   18:08   0:00 -bash           
cabox      695  0.0  0.2  15520  1132 pts/0    R+   19:36   0:00 ps aux          
cabox      696  0.0  0.1   8816   764 pts/0    S+   19:36   0:00 grep --color=aut
o cabox                                              
