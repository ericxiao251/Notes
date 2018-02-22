# How To Use SSHFS to Mount Remote Files Systems Over SSH
1. Install **Fuse** and **SSHFS** for Mac OSX:  
  https://osxfuse.github.io
2. Create a directory to mount to:  
  `sudo mkdir mnt/server/`
3. Mount the server to the folder:  
  `sudo sshfs -o allow_other,defer_permissions root@xxx.xxx.xxx.xxx:/ mnt/server`
4. To unmount:  
  `sudo umount mnt/server`
  `sudo diskutil unmount force mnt/server`

reference:   [link](https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh)
