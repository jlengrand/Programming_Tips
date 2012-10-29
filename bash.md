# BASH

## FLV to AVI conversion :

You will need ffmpeg

```bash
$ sudo apt-get install ffmpeg
$ ffmpeg -o /your/flv/file.flv -vcodec mpeg1-video \
 -acodec copy -ar 44100 -s 320x240 -y /your/avi/file.avi
 ```

## OGG to AVI conversion :

You will need mencoder

```bash
$ sudo apt-get install mencoder
$ mencoder out.ogv -ovc xvid -oac mp3lame -xvidencopts pass=1 -o Winner.avi
```

## Get the size of a file :

Here are two simple ways:

```bash
$ ls -s file
$ stat file-c %s
```

##Get the processing time of a function/script:

Simply run the same command prepended with time

```bash
$ time previous_command
```

## Get the number of arguments in command line:

Use the variable **$#** to get the number of arguments of previous command.

__**WARNING:** The name of the command stands for one argument!__

## Get the list of dependencies of a binary:

Simply run the same command prepended with ldd :

```bash
$ ldd previous_command
```

## Demonize a process :

The command to search for is **start-stop-daemon**, with start option.

To avoid any output in stdout, use redirection:

```bash
$ command &> /dev/null&
```

## Launch a process at startup:

A link must be placed in /etc/init.d, using ln -s

```bash
$ mv /etc/init.d
$ ln -s /path/to/file link
```

__**WARNING:** A printf in a startup process will lead to a crash as it blocks the remaining processes.__

__**INFO:** In embedded Linux, startup processes will have to be named using a Sxx name, where xx is a digit between 1 and 99.__

The processes will be run in ascending order, so be careful not to block the system (samba after network, . . . )

## Block interruptions (CTRL+C) :

Simply add the line

```bash
trap " 2 3
```

where you want to ‘trap’ the command.

End catching interruptions by adding where you want to stop

```bash
trap 2 3
```

## Use floats in a script, and convert them back to integers:

The operations can be performed with bc :

```bash
$ VAR=$(echo "2.2/ 10.65" | bc -l)
```

To switch back to the int value :

```bash
$ (ceil) INT=${VAR/.*}
```

## Search for pattern in all files of a folder:

```bash
$ "find ./ -name .svn -prune -o -type f -print | xargs grep -Hi" //pattern//
```

The .svn part is used to avoid searching in the subversion folder of my projects.

```bash
$ grep -R //pattern//@@ is also a solution.
```

It is even possible to create an alias with it (see Add a one line command in terminal).


 ##Add a one line command in terminal:

You may use some one-line commands lots of times a day in terminal.

You can define aliases to gain productivity:

```bash
$ vim ~/.bash_aliases
```

Simply add a new line at the end of the file :

```bash
alias_name = "my_one_line_command"
```

Restart your terminal, you’re done!

## Seconds since epoch:

```bash
$ date -d "$FIRST_TIME" +"%s"
```

## Directly get the correct shebang for you script:

```bash
$ which //language// > my_script
```

Example :

```bash
$ which bash > my_script.sh
```

## Get the encoding of a file:

```bash
$ file -i //unkown_file_type//
```

## Remove all .svn folders from a repo:

```bash
$ cd //my_folder///
$ find -name ".svn" -exec rm -rf {} \;
```

__**INFO:** Can be performed for any folder type, changing the .svn part__

## Get information about your Linux version:

Description file:
```bash
$ cat /etc/lsb-release
```

Kernel version:
```bash
$ uname -a
```

More information about Kernel (compiler and so on):
```bash
$ cat /proc/version
```

Get information about your processor(s):

```bash
$ cat /proc/cpuinfo
```

## Change default browser in Linux:

```bash
$ update-alternatives &&config x-www-browser
```

You will have to choose between all installed browsers in you distro.

## Add a user to the sudoers:

```bash
$ visudo
```

Search for the line

```bash
@@ root ALL=(ALL) ALL@@
```

Add this new line just below :

```bash
user_name ALL=(ALL) ALL
```

## Get information about you graphical card:

```bash
$ lspci | grep VGA
```

You may try this if first is not working :

```bash
$ lspci | grep video
```

## Add tab completion for sudo commands:

Add

```bash
complete -cf sudo
```

in your .bashrc. It can be done simply in running the following command once:

```bash
$ echo "complete -cf sudo" > ~/.bashrc
```

## Read information in elf files:

```bash
$ readelf -h $1 | grep 'Class\|File\|Machine'
```

## Sniff on serial interface to read output of a device :

```bash
$ sudo apt-get install jpnevulator
$ jpnevulator --read --ascii --tty /dev/ttyUSB0
```

## Remove trailing / in path in a script:

```bash
#!/bin/bash
FOLDER=$1
echo ${FOLDER%/}
```
