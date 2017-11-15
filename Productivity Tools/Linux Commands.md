# Linux/Unix/Bash Commands

shows the first `x` lines of file
```shell
head -x file.ext
```

# [Quick SSH Config Files](http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/)

1. Setup your SSH alias: `~/.ssh/config`
    ```
    Host dev
        HostName dev.example.com
        User username
    ```
2. Add your credentials:
[ssh-copy-id](https://linux.die.net/man/1/ssh-copy-id)

`ssh dev` will be equivalent to `ssh username@dev.example.com` with the password being saved.

# [Copying Files from Server to Local](https://linux.die.net/man/1/rsync)
`rsync [options] [source] [destination]`

Ex. `rsync -avzh xiaoe@130.113.103.46:~/filepath ~/localfilepath`
