# How to set the correct ssh configuration for UdeM astro servers
(this is taken from a previous Jason Rowe and Luc Turbide emails)
For more info  about ssh keys and config file, see these links:
- [My favorite example](https://docs.gitlab.com/ee/user/ssh.html)
- [Github: Check for existing keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)
- [Github: Generate new keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [Compute Canada](https://docs.alliancecan.ca/wiki/SSH_Keys)

## Access all astro server without password (using a key)
 
### Connect to venus or other astro servers
Example to connect to maestria via venus:
```
ssh -oport=5822 -t your_login_name@venus.astro.umontreal.ca ssh -oport=5822 maestria
```

### Generate the ssh key on the servers
```bash
$ cd
$ mkdir .ssh   (if .ssh does not exist)
$ chmod 700 .ssh
$ cd .ssh
$ ssh-keygen (Press ENTERs 3 times without writing anything)
$ cat id_rsa.pub >> authorized_keys
$ chmod 600 authorized_keys
```

### Generate a key on your local computer

1. After disconnecting from maestria (`exit` until your back on your computer), generate an ssh key using `ssh-keygen` (same as the previous step)
2. Copy the content of the file `.ssh/id_rsa.pub` from your computer into the file `.ssh/authorized_keys` on venus (so you need to [connect back](#generate-the-ssh-key-on-the-servers) to venus).


## Enter new configuration in ssh config file

On your computer edit `~/.ssh/config` (if it doesn't exist, create it):

- First, you need to define the Host that will be used for the proxy jump. Here it is `venus`.  
  You can  give it the  name you  want, but I use the same name, i.e. `venus`
```unix
Host venus
       HostName venus.astro.umontreal.ca
       User YourLoginName
       Port 5822
```

- Then, add the server of your choice that will use `venus` for the proxy jump.  
  The following lines show an example for a connection to `maestria` server.  
  The name is up to you. Here I chose `YourLoginName_maestria`.
```
Host YourLoginName_maestria
       HostName maestria.astro.umontreal.ca
       User YourLoginName
       Port 5822
       ProxyJump venus
```
Don't forget to change `YourLoginName` above to your user name on maestria.

Now, you should be able to connect to maestria simply  by typing: `ssh YourLoginName_maestria`.
