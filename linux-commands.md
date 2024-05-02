cat <file-name>

#!/bin/bash - shibang

to find directory/file
- which <directory/file - name>

. - current working directory
/ - in directory


read -> it will ask for input in command line

$# -> number of commandline args 
$@ -> list of commandline args
$* -> single string of command args 


# storing a value in a variable
variable_name=$(command)  or variable_name=`command`

# to make read-only variable or to restrict to change the variable
readonly variable_name 

# To unset the variable 
variable_name= #put it blank
unset variable_name

# Operations on string
 - curly braces must needed to do Operations
lower the first letter
${var^}
lower the all letters
${var^^}
upper the first letter
${var,}
upper the all letters
${var,,}

length of the string
${#var}

substring examples

string="abcmaheshabcxyz"
echo "${string:0}"     - from first letter and make a string of remaining                                   - abcmaheshabcxyz
echo "${string:1}"     - from second letter and make a string of remaining                                  - bcmaheshabcxyz
echo "${string:0:3}"   - the string from first letter to the next 2 letter - total letter are 3             - abc
echo "${string:3:3}"   - the letter which is placed on 3rd index to the next 2 letter - total letter are 3  - mah
echo "${string: -5}"   - Last 5 letter of the string                                                        - bcxyz
echo "${string#a*c}"   - remove the letter from first a letter in string to the first c after a             - maheshabcxyz
echo "${string##a*c}"  - remove the letter from first a letter in string to the last c after a              - xyz
echo "${string%b*z}"   - from  the last letter b to first letter z                                          - abcmahesha
echo "${string%%b*z}"  - from  the first letter b to last letter z                                          - a

sub-part replacement
abcmaheshabcxyz -> replacing the abc to xyz
${string/abc/xyz} -> only first abc will replace -> xyzmaheshabcxyz
${string//abc/xyz} -> all abc will replace -> xyzmaheshxyzxyz

sub-part removal
abcmaheshabcxyz -> removing abc
${string/abc} -> maheshabcxyz
${string//abc} -> maheshxyz


Setting the variable default value
variable_name=${variable_name:-value}
variable_name=${unsetvariable_name-value}

example:

ex1
name="" # variable is already set
xname={name:-Mahesh} # we have give the : because the variable is already set

ex2
yname={unsetvar-Ramesh}     # here we dont have to provide : because the unsetvar is never set before
