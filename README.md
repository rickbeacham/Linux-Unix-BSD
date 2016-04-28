# Linux-Unix-BSD
Research on OS operations

# Copy files without losing file/folder permissions
 Tar preserves file permissions
 
 1 - On the source computer:

cd /path/to/folder/to/copy
tar cvpzf put_your_name_here.tar.gz .

2 - Copy put_your_name_here.tar.gz to the USB drive and then to the other computer

3 - On the destination computer:

cd /path/to/destination/folder
tar xpvzf put_your_name_here.tar.gz
tar will recreate the archived folder structure with all permissions intact.

Those commands will archive the contents of the source folder and then extract them into the destination folder. If you want to copy the folder itself, then you should, at step 1:

cd /path/to/parent/folder
tar cvpzf put_your_name_here.tar.gz folder_to_copy
The same mechanism could be used for single files.

If you can connect from one computer to the other using ssh (rsync) -a flagg might be more practical.
	 	
I just did a quick test to be sure and -p is not needed -- tar preserves permissions by default, at least when the user owns the files being archived/extracted.
