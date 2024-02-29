# Bash Scripting

In order to define a bash script as being one, the line `#!/bin/bash` needs to be added at the top as it tells the computer which type of interpreter to use for the script. It is commonly considered good practice to save script files in the *~/bin/* directory.

Script files will also need to have permissions to allow them to execute, and can be done through the command line after entering the script's directory using the command `chmod +x <scriptName>.sh`.

Any file stored in the *~/bin/* directory can be run from anywhere just by typing the file name.

## Variables in Bash

Just like any other programming language, Bash can define variables: for example, `greeting="hello"` which can then be printed to the terminal using `echo $greeting`. It is important to note the lack of whitespace in variable declarations.

## Conditionals

Similarly, conditional statements can be implemented in Bash using the following operators:
- Equal `-eq`
- Not equal `-ne`
- Less than or equal `-le`
- Less than `-lt`
- Greater than or equal `-ge`
- Greater than `-gt`
- Is null `-z`

An example of a conditional statement is:
```
if [ $index -lt 5 ]
then
  echo $index
else
  echo 5
fi
```
It is worth noting a few key points about conditionals in Bash. Firstly, the spaces inside the square brackets ae mandatory, and secondly the condition must end in `fi`.

## Loops

Bash utilises three different loop structures: `for`, `while`, and `until`.

A for-loop may look like:
```
for integer in $numbers
do
  echo $integer
done
```

A while-loop may look like:
```
while [ $index -lt 5 ]
do
  echo $index
  index=$((index + 1))
done
```

An until-loop may look like:
```
until [ $index -eq 5 ]
do
  echo $index
  index=$((index + 1))
done
```

## Inputs

Bash uses the `read` syntax to take user input and assigns it to a variable: for example, `read number`. If the script is required to accept indefinite arguments, then you can iterate over them using:
```
for arg in "$@"
do
  echo $arg
done
```
You can of course assign or manipulate the input however is required.
You can also access files externally and assign them to a variable name using standard Bash pattern matching: for example, to get all the files in a directory, you add the `*` character `files=/some/directory/*`.

## Aliases
Aliases can be set up within the `.bashrc` or `.bash_profile` file to allow calling scripts without the full filename: for example, if we have a script called `myScript.sh`, we can alias it to the word `myScript` using the syntax `alias myScript='./myScript.sh'`.