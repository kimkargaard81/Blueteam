to find the creation time of a file on an ext4 file system use:

debugfs -R "stat <$(stat -c %i /var/log/messages)>" /dev/sda1 

