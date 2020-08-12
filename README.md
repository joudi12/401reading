# 401reading

---

## Command Line
- A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

- The command line typically presents you with a prompt. As you type, it will be displayed after the prompt. Most of the time you will be issuing commands.

## Basic Navigation!
- The first command we are going to learn is pwd which stands for Print Working Directory. (You'll find that a lot of commands in linux are named as an abbreviation of a word or words describing them. This makes it easier to remember them.) The command does just that. It tells you what your current or present working directory is. Give it a try now.

- ls List the contents of a directory.
- cd Change Directories - ie. move to another directory.
- pwd Print Working Directory - ie. Where are we currently.
- file obtain information about what type of file a file or directory is.
- ls -a List the contents of a directory, including hidden files.
- Everything is a file under Linux Even directories.
- Linux is case sensitive Beware of silly typos.
- To exit the man pages press 'q' for quit.
- n After performing a search within a manual page, select the next found item.
- Creating a directory is pretty easy. The command we are after is mkdir which is short for Make Directory.
- The command to remove a directory is rmdir, short for remove directory.
- In fact we can make use of this very characteristic to create blank files using the command touch.
-  we may wish to create a duplicate so that if something goes wrong we can easily revert back to the original. The command we use for this is cp which stands for copy
- to move a file we use the command mv which is short for move.
- As with rmdir, removing a file is an action that may not be undone so be careful. The command to remove or delete a file is rm which stands for remove.
- vi : Edit a file.
- cat : View a file.
- less : Convenient for viewing large files.

- Linux permissions dictate 3 things you may do with a file, read, write and execute. They are referred to in Linux by a single letter each.

    - r read - you may view the contents of the file.
    - w write - you may change the contents of the file.
    - x execute - you may execute or run the file if it is a program or script.
    For every file we define 3 sets of people for whom we may specify permissions.

    - owner - a single person who owns the file. (typically the person who created the file but ownership may be granted to some one else by certain users)
    - group - every file belongs to a single group.
    - others - everyone else who is not in the group or the owner.
    - Three persmissions and three groups of people. That's about all there is to permissions really. Now let's see how we can view and change them.
- Head is a program that prints the first so many lines of it's input. By default it will print the first 10 lines but we may modify this with a command line argument.
- Tail is the opposite of head. Tail is a program that prints the last so many lines of it's input. By default it will print the last 10 lines but we may modify this with a command line argument.
- Sort will sort it's input, nice and simple. By default it will sort alphabetically but there are many options available to modify the sorting mechanism. Be sure to check out the man page to see everything it may do.

- > Save output to a file.
- >> Append output to a file.
- < Read input from a file.
- 2> Redirect error messages.
- | Send the output from one program as input to another program.
- top View real-time data about processes running on the system.
- ps Get a listing of processes running on the system.
- kill End the running of a process.
- jobs Display a list of current jobs running in the background.
- fg Move a background process into the foreground.
- ctrl + z Pause the current foreground process and move it into the background.
## Useful Commands

- du -sh ./* Find the size of every directory in your current directory.
- df -h Display how much disk space is used and also free.
- basename -s .jpg -a *.jpg | xargs -n1 -i cp {}.jpg {}_original.jpg Make a copy of every jpg image file in the current directory and rename adding _original.
- find /home -mtime -1 Find all files in the given directory (and subdirectories) which have been modified in the last 24 hours.
- shutdown -h now Shutdown the system. (Replace -h with -r for reboot.)
