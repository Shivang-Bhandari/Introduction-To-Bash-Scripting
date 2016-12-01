# Introduction-To-Bash-Scripting
This Repository contains some key notes for beginners to get comfortable with Bash Shell Scripting

#### Abbrevations :

* apt : Advanced Package Tool

* dpkg : dpkg is the software at the base of the package management system in
the free operating system Debian and its numerous derivatives.
dpkg is used to install, remove, and provide information about .deb packages.

* RPM : RPM (Red Hat Package Manager) is an default open source and most popular
package management utility for Red Hat based systems like (RHEL, CentOS and Fedora).
The tool allows system administrators and users to install, update, uninstall,
query, verify and manage system software packages in Unix/Linux operating systems.

* YUM : YUM (Yellowdog Updater Modified) is an open source command-line as well
as graphical based package management tool for
RPM (RedHat Package Manager) based Linux systems. It allows users and system
administrator to easily install, update, remove or search software packages on a systems



#### These are some of the various commands used in Linux :

* who am i : this command helps find the time and date of the login by a user.

* pwd : displays current working directory (by default home/username/).

* cal : Viewing calender in the shell (for custom calender enter cal month(m) year(yyyy)).

* date : Viewing date time of the system.
          Customizing view : '+DATE : %m-%y%nTIME : %H:%M:%S' changes view to

          DATE : mm-yy
          TIME : hh:mm:ss

* touch : create new files.

* mkdir : make a directory in the current working directory.(mkdir [path] for a dir in a specified path)

* cd : change directory

* cat : reading a single file or concatenation of two or more files. (to read use cat < (filename) to overwrite use cat > (filename) )

// NOTE: To append some data to the file and not overwrite it use (cat >> )

* mv : renames files (mv foo boo changes the file with a file name foo to boo)

* rm : removes given file or directory (rm foo removes the file named foo). For removing a directory used command rm -r [dirname] or rmdir [dirname]

* cp : used to copy a file (cp old music\old creates a copy of the file in music)

* ln : it is the link comman used for keeping two files in sync so that changes
        made to one file can automatically be commited to the linked file.
        ln old new creates two files named old and new and whenever any one of These
        files experiences a commit the other one has automatic updataion accordingly.

        There is another type of link that is soft link in which there is a sort of
        shortcut file generated which when executed links directly to the mail file.
        To use this link the syntax is : ln -s old old_soft this generates a file named
        old and a soft link named old_soft which links to the old file.

* tty : Displays USers terminal name

* chmod : to change the file permissions of a certain file chmod is used to change the
           pre-existing file permissions. We use chmod then type in a numbe acc to our
           needs from the file permissions and then the file name for e.g. if a file has
           to be made readable and writable by all three types of users then the command
           used is chmod 777 filename this makes the permissions readableand writable
           by all three types of users.

* uname -a : displays all of your system info.

* file * : this command is used to display all contents of the pwd and their types.

* wc : displays the number of lines words and characters in a file.

* sort : used to sort data in a file alphabetcally.

* cut : the cut command is used to delete some sections of the document on the basis
         of what we want to display on the terminal,
         the command is executed as : cut -d(represents diffrenciating character)"d.c." -f (represents the fields to be displayed) 1,3 [filename]

* dd : used for conversions used as --> dd if = test of = test2 conv = ucase , here if in input file which we want to convert and of represents output files con = ucase turns all text to uppercase.

* banner : makes text appear in pattern of stars etc (fancy text).

* compress : used to compress files. used as compress -v filename
              the -v here is used to display the level of compression



