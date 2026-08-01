# File & Directory Operations
#Commands  							Description
touch								Create an empty file
mkdir								Create a directory
mkdir	-p							Create nested directory
cp	source	dest						Copy a file
cp	-r	srcdir	destdir					copy a directory
mv	source	dest						Move/rename a file/directory 
rm	<file>							remove a file
rm	-r	<dir>						remove a directory
rm	-f	<file>						force remove a file
rmdir	<dir>							remove empty directories

#finding files and links 
#Commands							Description
find	<path>	-name	"pattern"				Find both files and directories
find	.	-type {f,d,l,c,b}				Search for specific file or directory
locate	<name>							Quickly find files using prebuilt index
which	<command>						Show the full path of excecutable command
ln source(file you wanna to make) link(name of the hard link)	Create hard link						
ln	-s	source	link					Create soft link(pointing to a file or directory)
ln 	-sf	target 	linkname 				Force overwrite a link


