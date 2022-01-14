# Q1. What is absolute path and relative path?
Solu- 
Absolute path: It is defined as specifying the location of a file or directory from the root directory (/).   It is a complete path of a file from the start. E.g., cat /home/sub-dir/file.txt
Relative path: It is a path related to the present working directory. It starts with the current directory and not the root directory. E.g., cat Desktop/file1 

# Q2. What are hard links?
Solu-
A hard link is essentially a label or name assigned to a file. It is possible to create a number of different names that all refer to the same contents. Commands executed upon any of these different names will then operate upon the same file contents.  Even if you delete the original file, the hard link will still has the data of the original file. Because hard link acts as a mirror copy of the original file.

# Q3. What does /srv contains and why is it empty?
Solu-
The /srv/ directory contains site-specific data served by your system. This directory gives users the location of data files for a particular service, such as FTP or WWW. Data that only pertains to a specific user should go in the /home/ directory. 
/srv is empty sometimes as the system might not be hosting any server at that moment. 

# Q4. How does cgroups differ from namespaces?
Solu-
Namespace is a mechanism to limit the visibility that a group of processes has of the system. It makes is possible to run a whole range of application a single machine and ensure none of the other can interfere with one another. 
Cgroups is for limiting the use of resources by a group of processes running on the system. It is used by a group of processes running on a system. 
Mainly the namespaces do not restrict access to physical restrictions but in cgroups they can be restricted. 

# Q5. In vim how can we search inside a file?
Solu-
In vim by pressing escape and getting into the command mode then pressing / and then typing the pattern/word that we want to search the cursor move to it. 

# Q6. How to delete a file in vi editor?
Solu-
By opening a file and pressing escape and getting into the command mode, :!rm <filename> , using this the currently opened file will be deleted.

# Q7. Difference between wq and x?
Solu- 
If you :x a file in which no changes have been made, the modification time will be untouched because the file isn’t re-saved. The :wq command will alter the modification time no matter what.

# Q8. What are hidden files?
Solu- 
Hidden files in Linux are the files that are not listed when the user runs ls command. The name of a hidden file starts with a dot(.). Files are hidden in Linux as to make sure that users don’t accidentally modify the contents of these files or accidentaly delete these files. Or files could be hidden for privacy issues. Most hidden files contain environment settings or data that are accessed by programs being run by the user.
 
# Q9. How to identify which type file it is?
Solu-
We can identify a type of file by the colour of the files which are as follows:
-*Blue*: Directory
- *Green*: Executable or recognized data file
- *Cyan*  (Sky Blue): Symbolic link file
- *Yellow with black background*: Device
- *Magenta*  (Pink): Graphic image file
- *Red*: Archive file
- *Red with black background*: Broken link

