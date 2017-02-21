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


### AND Operator :
--------------


The Logical AND Operator is denoted by '-a'. While checking conditions

e.g. : ``[ num -le 50 -a num -ge 10] checks if num is less than 50 and greater than 10``


### OR Operator :
--------------


The Logical OR Operator is denoted by '``-o``'. While checking conditions

e.g. : ``[ $var = a -o $var = e -o $var = i $var = o -o $var = u ]``
checks if the character stored in the variable var is a vowel or not.



### Cases :
-------


For a given input by the user, there can be multiple checks which can be performed
using cases. If we have to find out the type of input stored in a variable
the cases can be : LowerCase, UpperCase, Digit, SpecialCharacter, More than one character

Command :

to initialize a case first we need to have a control variable on which the cases shall
be executed. Lets say the case variable is 'inp'

``case $inp in      //initializes the case in a script
[a-z])           // ) bracket tells shell to go furthur and execute statements for the case
      echo "LowerCase"
      ;;        // tells that the case statements have finished

[A-Z])
     echo "UpperCase"
      ;;

[0-9])
      echo "Digit"
      ;;

?)             // ? represents any 1 character on keyboard
      echo "SpecialCharacter"
      ;;

*)            // * represents multiple character input
      echo "multiple characters"
      ;;

esac        // case spelled backwards to indicate cases have been finished
``


## Loops :
=======



### While Loop :
------------

Syntax :

``while [ condition ]
do
    //statements
done``


* Incrementation : Lets suppose the loop control variable is by the name of count.
Then to increment the variable count by 1 everytime the loop executed the Syntax
would be :

count = `expr count+1`

* expr tells the shell to execute count+1 as an expression and the whole expression
  is in Accent Graves because we need count to be equal to the final outcome of the
  expression.

Example :

to print numbers from 1-10 using while loop :

``count = 1

while [ $count -le 10 ]         //condition
do
  echo $count                   // prints numbers
  count = `expr count+1`        // Incrementation
done                            // end of loop

``


### Until Loop :
------------

The until loop works somewhat like the while loop, The only difference in them is
that the while loop executes till the condition specified is true whereas Until
loop executes till the condition specified is false.

Syntax :

``until [ condition ]
do
  // conditions
done
``


### For Loop :
----------


The for loops works normally as in other programming languages. In Shell scripting
For loop works with the syntax on for in loop as of js. Moreover the loop control
variable need not be initialized before using it in the loop.

Syntax :

``for item in *
do
    // statements

done
``

#### Setting ranges in for Loop :

* In a for loop range can be defined in the following way : for i in {l..g..i}

* Here, l is the lower limit, g is the greater limit and i is the Incrementation.
  for e.g. for i in {1..10..1} is equivalent to for(i=1;i<=10;i++)
  
  
----------
  
### grep :

Grep is a command which helps find certain words or a set of words in a specified
document which is given in as an argument while execution of the command. Syntax
to use the grep command is : grep {word to find}      

Grep has furthur options to make the search word case insensitive by using `-i` in
front of the word to find and also print the line in which the word is by using
`-n` in front of the word and to display both the -i and -n can be written in any
order.    

If we use `-c` in the command then the output is the number of lines in which the
word is occuring.

The `-v` option when used in the grep command it reverses the output that is it
displays all the lines as output in which the word to find does not exist.

`NOTE: for other options refer man grep`


--------------------------
### Internal Field Seperator :

Whenever we use the set command we notice that the shell automatically allocates
words to positional parameters. This works with the help of internal Field
Seperator. By default the value of the ifs is set to `" " (space character)`
i.e. it uses space character to diffrentiate and then use positional parameters.    

We can modify the behaviour of the set command using shell scripts.
To change the default value of the IFS in the shell just add a line in the script
before the set command is used.

`Add : IFS = (whatever you want to keep as the  seperating value for an input)`


----------------------------------------
### Reading inputs from pre-existing files :



In shell we can read inputs from pre-existing files using the exec command.


`NOTE: Refer to the shell script made in ubuntu for furthur understanding`




-------
### Sleep :


The sleep command is used to create a time lag while an output is being displayed
on the terminal. Syntax for the sleep command is : `sleep [no. of seconds]`  
for e.g. if we run a for in loop for a string input by the user then print out each
word one by one and run a sleep command with input 2 then, each word will be
displayed after 2 seconds of the previous word.

Syntax Example : `sleep 2`
this generates a time gap of `2 seconds` between two events.



-----------------------------------------------
### Script to replace -wc for word and line count :


As `-wc` is a command itself to find out the number of lines as well as words in a
specified file which is given as an argument, we can also create a script which
does the same work.

Initially we need to store the terminal default settings so that they can be restored
later using the exec command as done in a previous script `check printnumber in ubuntu`
       
Then we need to execute the file on the current terminal using the `exec command`.
Set two variables `'nol'` and `'now'` for number of lines and number of words namely
and set their initial value to `0` so that garbage value isnt picked up.      

Then run a while loop which reads the control variable for input, now increment
the nol for every new line in the document. For incrementation of the now variable
first for each line use the set command and set the positional parameters for each
word and then using `$#` for each line increment the number of words in a line in the
now variable and in the end echo out the output.


`NOTE: Dont forget to execute the default terminal settings in the end of the script`


 ----------
### Continue :

 The continue statement in bash when executed tells the shell to skip all the commands
 in the block and continue on with the block after the incrementation or leave the
 block permanently if the incrementation no longer affects the loop condition.

 In a while loop which prints numbers from 1-10 if we add an if block with the
 condition of control variable being equal to 5, and in the if block we simply
 execute the command continue, then, the furthur statements of the block wont be
 executed and the output for 5 will not be echoed out to the terminal.


 -----------------------
 ### The ';' Metacharacter :

 The ';' Metacharacter is used when the shell is to be `instructed that multiple
 commands are to be executed one by one in order from left to right`, otherwise
 without it the terminal throws error as multiple commands cant be executed at once.
 For example if ls cal banner "Hi" is directly run it would throw an error in the
 terminal but if we write it as ls; cal; banner "Hi" then the terminal will execute
 the commands one by one from left to right.


------------------
### grep application :

Previously we used grep to find out a pattern in a given file provided as an argument,
To find a pattern and store it in a new file named 'pattern' there is a single
line command without using if-else constructs.     

`Command : grep -i [word] [file] > pattern && echo "Done"`     

This command first makes the grep search Case insensitive and searches in the given
file. `The '>' symbol refers to redirection`, i.e. The output of the grep command is
then sent to the file pattern and when this is succesfully done it prints out Done on
the terminal.


-----------
### Functions :


Functions in bash are pretty much the same as in any programming language. In bash
any function can be defined and then used in the terminal by just using the function
name once the script is executed.    
To execute the script first we need to give the file executing permissions using
chmod +x command and then execute the script by using command '. filename.sh'    

`NOTE: space between . and filename is necessary to execute the shell script`     

We cannot execute the script directly using sh as it creates a new subshell and then
executes the script in it due to which the outer shell doesnt have access to the
shell where the script is being executed and therefore the shell cant access
the functions which are made in the script.

example :

`greet()    
{     
  echo "Good Morning !"      
}     
`
greet is a function which when run in a shell as a command will echo out Good Morning !


##### Unset : 

The unset command when run along with a function name givent to it
as an argument it will then make the function disabled that is make it undefined
and then when a command same as the funciton name will be run in the terminal
The terminal will throw an error of command not found.


----------------------------
### Executing Multiple Scripts :

When in a script if furthur linking is required to a script which exists we can
link a script in a script by simply adding `sh script.sh` in the end of the parent
script.      

`NOTE: here script.sh is referred to any script which is to be linked`

