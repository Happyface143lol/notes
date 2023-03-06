# Linux
### Terminal

```
pwd #Shows the current working directory.

clear #Clears the terminal.

[command] --help #Shows more information on how to use the command or program.

man [command] #Turns the terminal into a page with a description of the command and its options. 
	# We can use the arrows or `B` and `Spacebar` to skip up and down by a full page. 
	# We can use `/word` to search for a word. 
	# We can move between hits by using `N` and `Shift + N`. 
	# To quit, use `Q`.

cd [path] #Changes the shell's current directory.

cd #Returns to your home directory.
cd .. #Goes back to the parent of this current directory.
cd ~ #It means cd Users/saku143
cd - #Goes back to the previous directory

# if it starts with /, it means that it searches from the root of the computer. (Absolute path)  
# if not, it starts from where we are. (Relative Path)

ls [path] # Lists the contents of the [path] directory.

ls -F # Indicates the type of files and directories.
    	# / Indicates it's a directory.
	# @ Indicates a link.
	# * Indicates it's an executable.
ls -l # Shows additional information, such as file size and time of its last modification
ls -h # This makes the information human readable.
ls -r # Lists the contents of a directory in reverse.
ls -t # Lists items by time of last change instead of alphabetically.
ls -a # Stands for show all, including the hidden files.
ls -s # Shows the size of the files and directories
ls -S # Sorts the files and directories by size
ls -R # Lists all the nested subdirectories within a directory.
ls -FR #List recursively the new directory hierarchy we just created in the project directory

mkdir [path] # Makes a directory.
mkdir -p # Allows to create a directory with nested subdirectories in a single operation.
# Don't use spaces, begin with -, and stick with letters, numbers, periods, dashes and underscores.

nano my_file.txt # Creates a file, and runs a text editor.
# We can use Ctrl + O, to write our data to disk. 
# We can use Ctrl + X, to quit the editor.

touch my_file.txt # Creates a file, and it contains no data. 

rm [path] # Removes a file.
rm -i my_file.txt # Ask for confirmation before removing a file. 

mv [old] [new] # Renames a file
mv -i thesis/draft.txt thesis/quotes.txt # Ask for confirmation before overwriting files
mv x.txt .. # Moves the file to the parents directory
mv thesis/quotes.txt # Moves the file to the current directory

cp [old] [new] # Copies a file. If it's given more than one file, it copies it to a directory, and it copies it to the last argument.
cp -r thesis thesis_backup # Copies a directory

*.txt # Represents zero or more characters. It's a wildcard.
p*.txt # Only shows files that start with p.

?.txt # Only represents one character. It's also a wildcard.

#The wildcards can be combined.
#When the shell sees a wildcard, it expands the wildcard to create a list of matching filenames before running the preceding command. As an exception, if a wildcard expression does not match any file, Bash will pass the expression as an argument to the command as it is.


```


