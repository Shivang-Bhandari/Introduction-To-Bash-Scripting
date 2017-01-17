# Introduction-To-Bash-Scripting

This Repository contains some key notes for beginners to get comfortable with Bash Shell Scripting



### Abbreviations :



* ``apt`` : Advanced Package Tool

* ``dpkg`` : dpkg is the software at the base of the package management system in the free operating system Debian and its numerous derivatives. dpkg is used to install, remove, and provide information about .deb packages.



* ``RPM`` : RPM (Red Hat Package Manager) is a default open source and most popular package management utility for Red Hat based systems like (RHEL, CentOS and Fedora). The tool allows system administrators and users to install, update, uninstall, query, verify and manage system software packages in Unix/Linux operating systems.



* ``YUM`` : YUM (Yellowdog Updater Modified) is an open source command-line as well as graphical based package management tool for RPM (RedHat Package Manager) based Linux systems. It allows users and system administrator to easily install, update, remove or search software packages on a systems


### These are some of the various commands used in Linux :

* ``who am i`` : this command helps find the time and date of the login by a user.

* ``pwd`` : displays current working directory (by default home/username/).

* ``cal`` : Viewing calendar in the shell (for custom calender enter cal month(m) year(yyyy)).

* ``date`` : Viewing date time of the system. Customizing view : ``'+DATE : %m-%y%nTIME : %H:%M:%S'`` changes view to

          DATE : mm-yy

          TIME : hh:mm:ss
          
* ``touch`` : create new files.

* ``mkdir`` : make a directory in the current working directory.(mkdir [path] for a dir in a specified path)

* ``cd`` : change directory

* ``cat`` : reading a single file or concatenation of two or more files. (to read use cat < (filename) to overwrite use cat > (filename) )

`` NOTE: To append some data to the file and not overwrite it use (cat >> ) ``

* ``mv`` : renames files (mv foo boo changes the file with a file name foo to boo)

* ``rm`` : removes given file or directory (rm foo removes the file named foo). For removing a directory used command rm -r [dirname] or rmdir [dirname]

* ``cp`` : used to copy a file (cp old music\old creates a copy of the file in music)

* ``ln`` : it is the link common used for keeping two files in sync so that changes made to one file can automatically be committed to the linked file. ln old new creates two files named old and new and whenever any one of These files experiences a commit the other one has automatic updating accordingly. There is another type of link that is soft link in which there is a sort of shortcut file generated which when executed links directly to the mail file. To use this link the syntax is : ln -s old old_soft this generates a file named old and a soft link named old_soft which links to the old file.

* ``tty`` : Displays USers terminal name

* ``chmod`` : to change the file permissions of a certain file chmod is used to change the pre-existing file permissions. We use chmod then type in a number acc to our needs from the file permissions and then the file name for e.g. if a file has to be made readable and writable by all three types of users then the command used is chmod 777 filename this makes the permissions readable and writable by all three types of users.

* ``uname -a`` : displays all of your system info.

* ``file *`` : this command is used to display all contents of the pwd and their types.

* ``wc`` : displays the number of lines words and characters in a file.

* ``sort`` : used to sort data in a file alphabetically.

* ``cut`` : the cut command is used to delete some sections of the document on the basis of what we want to display on the terminal, the command is executed as : cut -d(represents differentiating character)"d.c." -f (represents the fields to be displayed) 1,3 [filename]

* ``dd`` : used for conversions used as --> dd if = test of = test2 conv = ucase , here if in input file which we want to convert and of represents output files con = ucase turns all text to uppercase.

* ``banner`` : makes text appear in pattern of stars etc (fancy text).

* ``compress`` : used to compress files. used as compress -v filename the -v here is used to display the level of compression

------------

## Starting Shell Scripts


### Common Commands

* ``echo`` : Echo command is used to display a simple statement on the terminal while running a shell script. for e.g. if we write ``echo "Hello World"`` it will display Hello World whenever the shell script is run.

* ``read`` : Read command is used as a scanf as it allows you to fetch data from the user and then store it in a variable and use it further in a given script.

``When you have to use a given variable in which a certain user input is stored,

Always write $var_name (syntax for proper execution). The $ symbol tells the shell that

what follows now is a variable name and it looks in the memory to find what is the value

of the same and then displays is at specified in the script.``

-----------

### Positional Parameters


A positional parameter is a variable within a shell program; its value is set from an argument specified on the command line that invokes the program. Positional parameters are numbered and are referred to with a preceding ``$'': $1, $2, $3,`` and so on.

* set : Set when followed by a string assigns each word of the string to a positional parameter. for e.g if a person types set ``i am awesome`` in the terminal, after pressing enter $1 will have stored 'i' $2 : 'am' and $3 : 'awesome'. to print all of this together command is '$*'.

* Accent Graves : The Accent Graves(\`\`) is used to run a command within a shell command for e.g. if we want to assign a files text to positional parameters then to do so one can use the command set cat filename but to make the terminal aware to execute cat filename first and then run set command on the returned output by the cat command we include the cat filename in accent graves making the correct command to be used : set \`cat filename\`.

* To find out the number of positional parameters that are in use the command is '$#' The number of total parameters set are stored in #. Using the command $# displays the number of parameters in the specified path.


--------------

### Mathematical Operations 

To perform Mathematical operations on two numbers first either assign two variables with two values or get the input from the user and then further display the result using echo command.


The command is : 

* ``expr $var1 + $var2``    (Addition)

* ``expr $var1 - $var2``    (Subtraction)

* ``expr $var1 \* $var2``   (Multiplication)

* ``expr $var1 / $var2``    (Divide)

* ``expr $var1 % $var2``    (Modulus)


``In the case of Multiplication we have added a ' \ ' before the Multiplication

symbol, that is to tell the terminal to treat * as a Multiplication symbol and not as

referer to all command.``


For a proper output on terminal the command in which mathematical operations are being performed will have to be within Accent Graves so that their output can then be displayed using the echo command.


------------

### Precedence of Operators



In case of shell scripting, the Precedence for mathematical operators is that Division, Multiplication and Modulus are on the same level and Addition and Subtraction are on the same level of Precedence although Multiplication, Division and Modulus have higher Precedence than that of Addition and Subtraction.


Order :  

1. /, \*, %    

2. +, -



### Float Number Operations :


For performing Mathematical Operations with float type values saved in variables the command has to be followed by ``'| bc'`` . bc here refers to an inbuilt precision calculator in the shell and helps output the result with float type inputs too.

For e.g. for Addition on two variables var1 and var 2 the command will be :


``
var3 = `echo $var1 + $var2  bc`

``
``
echo var3
``
-------------

### Escape Sequences :

* ``\n`` : Used to make text print in next line.

* ``\r`` : Prints whatever is followed by it and ignores the rest in the echo command.

* ``\t`` : Used to insert a tab while printing any statement.

* ``\b`` : Used to eat up the previous character in the echo command, be it a whitespace,or a non-white space. (Sort of a backspace).


--------------------------

### To print in a custom way :


* Bold : To print out bold text a custom code has to written before the statement is specified i.e. ``\033`` and then further specify the code to initiate the bold command i.e. ``[1m`` and then start on with the statement.

for e.g, if the statement is ``Hello World`` then to print it in bold in the terminal the command is :

``echo "\033[1mHello World"``

This command will print ``Hello World`` and everything after it in bold which is not what we want.

To terminate the bold command after a certain text write \033[0m

The Final Correct Command is : echo "\033[1mHello World\033[0m"


* Invert Colors : To Print a line in inverted colors of your terminal scheme the command which is to be executed after ``\033`` is ``[7m`` and to set things to normal ``[0m`` like above.



--------------

### tput Command :


The tput command can be used in multiple ways to perform simple operations on terminal.


Some of the illustrations are :


* ``tput clear`` : this not only clears the rubbish data on terminal but also the prompt from the terminal and gives back a clean terminal.

* ``tput lines`` : This prints out the number of lines in the terminal.

* ``tput cols`` : This prints out the number of columns in the terminal.

* ``tput cup [row] [col]`` : this is a command which transfers the cursor to the given location of row and column provided by the user as an argument initially in the terminal.

* ``tput bold`` : This turns on the BOLD mode. To turn back to normal use the format command ``\033[0m``

-------------

### if-then statements :

The usage of if-then statements in shell is slightly different than that of in other programming languages.

If we write a shell script to rename a file to a input provided by the user, the shell will first check if a file of the given name exists in the system and then it will rename it to the given input by the user. If we have to generate a log that the command was executed properly then we use the if-then statements.


``if mv orignalname newname

then

echo "Executed"

fi
``

Here shell executes the mv command and then executes the if block

if the statement has been executed then the echo command will be executed else

nothing will happen. The 'fi' here is a syntax used to tell the shell that the if

block has ended. In other words it defines the scope of the if block.



-------------------------

### if-then else statements :


It just adds an else statement in the previous if-then statements description which adds another echo statement which displays and message in the terminal when the command hasnt been executed properly or there was any error.


Syntax :



``
if mv orignalname newname  

then  

echo "Executed"  

else  

echo "Not Executed"  

fi``

### Checks On Numbers :
-------------------


To create checks on numbers which have been input by the user the syntaxes are :

1. lt : less than
2. gt : greater than

suppose there is a variable named varnum holding the value of user input. To check
a number is greater than or less than a given condition (suppose 30)
then the syntax to check it would be :

``[$varnum -lt/gt 30 ]``

this command can be used in an if else block to act accordingly if the statement
is true or false.



### Check on Files :
----------------

If a variable named varname has the user input for the filename that is to be checked
Checks on files can be performed using a simple syntax : [-f $varname]
similarly many filetypes can be checked by simply replacing -f in the command

The various types which can be checked are :

``-d`` : Directory

``-c`` : Character Special Files

``-b`` : Media Files

``-r`` : Read Permission

``-w`` : Write Permission

``-x`` : Execute Permission

``-s`` : File Size (Helps determine file size is greater than zero)


### Checks on Strings :
-------------------

Suppose there are two variables with string inputs then below are some of the Checks
one can perform on the strings :

Let variable names be str1 and str2

NOTE: Variables are kept in double-quotes to treat them as strings

1. ``Equality`` : ``[ "str1" = "str2" ]``

2. ``UnEquality`` : ``[ "str1" != "str2"]``

3. ``Non-Zero Length String`` : ``[ -n "str1" ]``

4. ``Zero Length String`` : ``[ -z "str1" ]``


 NOTE: If the result is True then answer is 0 else 1. To check the result use
 command echo $? after the command
