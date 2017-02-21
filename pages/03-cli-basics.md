# Command line basics

## Living in the Command Line

Web programmers have to live on the command line. It gives us fast, reliable, and automatable control over computers. Web servers usually don't have graphical interfaces, so we need to interact with them through command line and programmatic interfaces. Once you become comfortable using the command line, staying on the keyboard will also help you keep an uninterrupted flow of work going without the disruption of shifting to the mouse.

## What is Terminal?

Terminal is a modern version of an 'original' User Interface for unix based computers. At that time a Text Terminal is all you would have seen, no windows, no mouse. Because of this history, it's very powerful but sometimes a little cryptic.

Don't worry though, with a bit of practice you'll be flying around like a pro!

Although they technically mean slightly different things, the following terms are types of Terminal Environment

Shell
bash ('Bourne-Again shell')
Command Line
Text Terminal
DOS Prompt (on windows machines)
SSH (on remote machines)
Bourne Shell
csh
ksh
sh
UNIX Shell

## Paths

A path is a map to a location on a computer. On windows all file paths start with a drive letter. For example, `C:\` is your main hard drive. On *nix based operating systems (mac included) the file paths start with `/` and always use FORWARD SLASH (`/`) instead of BACK SLASH (`\`). Since we're using git bash we will have *nix like paths even though we are on windows.

To see your current path type `pwd` which is short for "present working directory" if you are in `~` you should see something like `/c/Users/YOUR_USER_NAME` the `/c/` is the *nix mapping for `C:\` to indicate you are in the C drive.

**Absolute Paths** an absolute path is an exact address to a file and will always start with `/`. The output of `pwd` is the absolute path to your present location.

**Relative Paths** a releative path is the relative path between to locations.

## Navigating between directories and listing files

To change directories we use the `cd` command. It can take absolute or relative paths.

For an example of how to use absolute paths try the following...

```
pwd  -  outputs your current path
cd /  -  changes to the root path (absolute)
pwd  - outputs your current path /
```

To navigate back to your home directory try typing `cd ` followed by the path that was output by the first `pwd` command.

From here we can try some relative navigation. Type `ls` this will list all the files and directories. Anything with a `/` after it is a directory.

Go to your desktop by typing `cd Desktop`. That was a relative path navigation. You didn't type the full path but the relative path from your current location "Desktop". To go back type `cd ..` this goes up one level relative to your current location.

These can be chained together. Try the following exercises

* `cd Desktop` - go back into Desktop
* `pwd` see the current path
* `ls` - list files on desktop

* `cd ../Documents` - go up one level then into Documents
* `pwd` see the current path
* `ls` - list documents

* `cd ../..` will go up two levels
* `pwd` see the current path (should be the users folder)
* `ls` - list users

You can also use paths directly with ls so you can type something like `ls ~/Desktop` to list the files on your desktop regardless of where you are on the computer.

## Tab completion and history

Modern shells offer tab completion to reduce the amount of typing needed.

To see this in action simply try the following...

```
cd ~/Des[TAB]
```

This can be done at any point in a filename so you don't need to type the whole thing manually.

You can also use the up / down arrow to go through previously typed commands. Just press up / down in the command prompt to see this in action.

You can also type `history` to see a full history of every command you've ever typed.

## View file contents

Any text file can be viewed using the `cat` command. Change directories to the root of this repo and try typing `cat readme.md` to see the contents of the readme file.

You can also type `code readme.md` to open the file in vs code.

## Piping

You can use the pipe character (`|`) to link commands together.

One extremely common command is `grep` which simply searches text.

Try typing `cat readme.md | grep git` this will output only lines of the readme.md that contain the letters "git".

You can also do this with the `history` command. `history | grep git` will give you only git commands you've used.

Another common command is `sort` you could do `cat readme.md | sort` which will sort the lines of the file alphabetically.

## Creating directories

To create a directory you can type `mkdir DirectoryName`

Then you can navigate into that directory `cd DirectoryName`

## Redirecting output

You can use the `>` character to redirect the ouptut.

So using the above example you could do `cat readme.md | grep git > somefile.txt` that will create a new file called `somefile.txt` that contains the result of that command (instead of outputting it to the screen).

## Creating files

You can use the `touch` command to create files. Simply type `touch myfile.txt` to create an empty file called `myfile.txt`

You can use `echo` to output text `echo "something here"` will output the "something here" to the terminal. You can also redirect that echo to a file `echo "somethign here" > anotherfile.txt` will create a new file with "something here" as the contents.

## Delete files.

Deleting from the command line can be very dangerous THERE IS NO RECYCLING BIN so any delete action is absolutely permenent.

To delete the file created in the last step use the `rm` command (short for remove) liek this `rm myfile.txt` will delete myfile.txt.

## wildcards

Wildcards allow you to filter files. These wild cards work on any of the commands (ls, rm, etc) so you can easily delete all of your files by using rm incorrectly.

To see this in action lets create some more files run this `touch blah.aaa blah.bbb blah.ccc blah.ddd blah.eee`

Try the following and look at the output:

```
ls *.txt
ls *.aaa
ls blah.*
```