# shell-scripting

## What is Shell Scripting?
Shell script consists of a set of commands to perform a task </br>
All the commands execute sequentially. </br>
Some tasks like automation, repetitive task, make jobs. </br>

## Scripting Format </br>
#!/bin/bash </br>

## Types of Shell
Bourne Shell (sh) </br>
Bourne Again Shell (Bash) <br>
Korn Shell </br>
C Shell </br>
TCsh Shell </br>

======================================</br>
$ mkdir scripts </br>
$ ls -ltr </br>
$ cd scripts </br>
$  echo $0  (print the shell name) </br>

$ vi test_script.sh </br>
#!/bin/bash </br>

echo Hello </br>

$ ls -ltr </br>
$ ./test_script.sh </br>
o/p: Permission denied </br>
$ chmod u+x test_script.sh </br>
$ ./test_script.sh </br>
o/p: Hello </br>
====================================== </br>

Variables in Script </br>
var_name=value </br>
var_name=$(hostname) </br>

Echo $var_name </br>

$ vi variable.sh </br>
#!/bin/bash </br>

name=Prachi </br>
age=23 </br> 

echo My name is $name and my age is $age </br>

$ chmod u+x variable.sh </br>
$ ./variable.sh </br>
o/p: My name is Prachi and my age is 23. </br>

$ vi variable.sh     (to print Linux command output) </br>
#!/bin/bash </br>

name=Prachi
age=23

echo My name is $name and my age is $age

host=$ (hostname)
Echo My hostname is $host

$ ./variable.sh </br>
o/p: My name is Prachi and my age is 23. </br>
My hostname is test </br>
======================================= </br>

How to take input from user? </br>
Read <vr_name_to_stoore_value> </br>

$ Vi input_user.sh </br>
#!/bin/bash </br>

echo What is your name? </br>
read name </br>

echo Hi $name, Welcome </br>

$ chmod u+x user_input.sh </br>
$ ./user_input.sh </br>
=================================== </br>

If-else condition </br>
If [ $age -eq 18 ] </br>
Then
        echo “You are eligible to vote” </br>
else </br>
        Echo “Sorry you are not eligible to vote” </br>
fi </br>

$ if_else.sh </br>
#!/bin/bash </br>

echo Hi user, Welcome to the Election </br>
echo What is your age? </br>
Read age </br>

If [ $age -eq 18 ] </br>
then </br>
         Echo You can vote! </br>
else </br>
        Echo Sorry You cannot vote! </br>
fi </br>
     
$ chmod u+x if_else.sh </br>
$ ./if_else.sh </br>

Types of Operators </br>

Equal </br>
-eq/== </br>
Greaterthanorequalto -ge </br>
Lessthanorequalto -le </br>
Not Equal -ne/!= </br>
Greater Than -gt </br>
Less Than -lt </br>

$ if_else.sh </br>
#!/bin/bash </br>

echo Hi user, Welcome to the Election </br>
echo What is your age? </br>
Read age </br>

If [ $age -ge 18 ] </br>
then </br>
         Echo You can vote! </br>
else  </br>
        Echo Sorry You cannot vote! </br>
fi </br>
 
$ ./if_else.sh </br>
o/p: Hi user, Welcome to the Election </br>
       What is your age? </br>
user writes: 18 </br>
o/p: You can vote! </br>

$ ./if_else.sh </br>
o/p: Hi user, Welcome to the Election </br>
       What is your age? </br>
user writes: 27 </br>
o/p: You can vote! </br>

========================================================= </br>

Switch case </br>
#!/bin/bash </br>

echo Hey choose an option </br>
echo
echo a = To see the current date </br>
echo b = list all the files in current dir </br>

read choice </br>

case $choice in </br>
date;; </br>
Ls;; </br>
      *) echo “Non a valid input” </br>
esac </br>

$ vim case_script.sh </br>
#!/bin/bash </br>

echo Press any option </br>
Echo 1=show date </br>
echo 2=List files in current dir </br>
echo 3=Show current path </br>

Read choice </br>

case $choice in </br>
Date;; </br>
Ls -ltr;; </br>
pwd;; </br>
echo Invalid input </br>
esac </br>

$ chmod u+x case_script.sh </br>
$ ./case_script.sh </br>
o/p:  1=show date </br>
        2=List files in current dir </br>
        3=Show current path </br>
user writes: 1 </br>
o/p: Sun Aug 07 16:04:18 EDT 2022 </br>

$ ./case_script.sh </br>
o/p:  1=show date </br>
        2=List files in current dir </br>
        3=Show current path </br>
user writes: 2 </br>
o/p: list the directories </br>
 
For Loop </br>
for i in 1 2 3 4 5 </br>
do </br>
	echo Number is $i </br>
done </br>

otherways to write For loop </br>
For j in eat Raju Sham </br>
For p in {1..20} </br>

$ vim for_loop.sh </br>
#!/bin/bash </br>

for num in 1 2 3 4 5 </br>
do </br>
	echo Number is $num </br>
done </br>

$ chmod u+x for_loop.sh </br>
$ ./for_loop.sh </br>
o/p: Number is 1 </br>
       Number is 2 </br>
       Number is 3 </br>
=========================== </br>
$ vim for_loop.sh </br>
#!/bin/bash </br>

for num in 1 2 3 4 5 </br>
do
	echo Number is $num </br>
Done </br>

$ ./for_loop.sh </br>
o/p: Number is 1 </br>
       Number is 2 </br>
       Number is 3 </br>
       Number is 4 </br>
       Number is 5 </br>
       Number is 6 </br>
       Number is 7 </br>
       Number is 8 </br>
       Number is 9 </br>
       Number is 10 </br>


$ vim for_loop.sh </br>
#!/bin/bash </br>

for num in (1..3) </br>
do </br>
	echo Number is $num </br>
done </br>

for task in Read Write Blog Video Sleep Eat </br>
do  </br>
	echo My task is $task </br>
done  </br>

$ ./for_loop.sh </br>
o/p: Number is 1 </br>
       Number is 2 </br>
       Number is 3 </br>
       My task is Read </br>
       My task is Write </br>
       My task is Blog </br>
       My task is Video </br>
       My task is Sleep </br> 
       My task is Eat </br>
======================================= </br>
While Loop </br>
count=0 </br>
num=10 </br>

while [ $count -le $num ] </br>
do  </br>
       echo Numbers are $count </br>
       let count++ </br>
done </br>

$ vim while_loop.sh </br>
#!/bin/bash </br>

num=10 </br>
count=0 </br>

while [ $count -le $num ] </br>
do  </br>
	echo $count </br>
	let count++ </br>
done </br>

output: </br>


================================= </br>

Iterate values from file </br>
 hosts=”<path_of_the_named_items>” </br>

For item in $(cat $items) </br>
do </br>
       echo $item </br>
done  </br>

$ vim name </br>
Raju </br>
Shyam </br>
Babu bhai </br>

$ pwd </br>
/home/prachi/scripts </br>

$ vim file_iterate.sh </br>
#!/bin/bash </br>

names=”/home/prachi/scripts/name” </br>

for name in $ (cat $names) </br>
do  </br>
	   echo Characters of Hera Pheri is $name </br>
done  </br>

$ chmod u+x file_iterate.sh </br>


$ ./file_iterate.sh </br>
Output: </br>


================================= </br>
How to use expression </br>
Using  let command </br>

Example: </br>
let a++ </br>
let a=5*10 </br>

Alias </br>
alias <short_name>=”<your_command>” </br>

Example: </br>
alias  </br>
alias d=”ls -ltr | awk ‘(print \$9)’” </br>
alias pchron=”ps -ef | grep” </br>
Output: </br>
 
