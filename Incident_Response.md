to view inside a zip file - This can be used to see what is inside a zip archive without having to unzip the file. The zipinfo tool is installed on Kali.
zipinfo file.zip

to get a hash of a file within a zip, use the following command:

unzip -p zipfile.zip filename | md5sum 

This will provide the md5 hash of the file within the zip. Of course, it is perfectly possible to use sha1sum or any other hash type instead of md5sum.


