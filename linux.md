# Linux
### Terminal

`ls` Lists the contents of the current directory.

```
-F: (with ls) Indicates the type of files and directories.
	/ Indicates it's a directory.
	@ Indicates a link.
	* Indicates it's an executable.
-l: Shows additional information, such as file size and time of its last modification
-h: This makes the information human readable.
-r: Lists the contents of a directory in reverse.
-t: Lists items by time of last change instead of alphabetically.
-a: Stands for show all, including the hidden files.
-s: Shows the size of the files and directories
-S: Sorts the files and directories by size
```

`pwd` Shows the current working directory.

`clear` Clears the terminal.

`↑ and ↓` To access the previous commands by going line-by-line.

`--help` Shows more information on how to use the command or program.

`man` Turns the terminal into a page with a description of the command and its options. We can use the arrows or `B` and `Spacebar` to skip up and down by a full page. We can use `/word` to search for a word. We can move between hits by using `N` and `Shift + N`. To quit, use `Q`.

`cd` Changes the shell's current directory.

//cd alone returns to your home directory.

//if it starts with /, it means that it searches from the root of the computer. (Absolute path)  
//if not, it starts from where we are. (Relative Path)

```
~: Means the current user's home directory. Only works if it's the first in the path.
-: Previous directory I was in.
```

`/` If it appears at the front of a file or directory name, it refers to the root directory. When it appears inside, it's just a separator.
`..` Means the parent of this current directory. 
`.` Refers to the current working directory.


