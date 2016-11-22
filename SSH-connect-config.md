# Use Config file to connect to TC
* 1. move to your `~/.ssh`, add a `rsa key` use code:(On your PC)
```
ssh-keygen -t rsa
```
here you need to input you `rsa` file's name and a password(empty suggest, click `Enter` to escape)
* 2. Log in your account on TC, come to you home directory(On TC)
```
mkdir .ssh
```
* 3. Use `scp` to upload the `.pub` file(On your PC)
```
scp /path/xxx.pub username@hostname:~/.ssh
```
* 4. Let TC know your key(On TC)
```
cat xxx.pub >> authorized_keys
chmod 700 ~/.ssh/
chmod 600 authorized_keys
# restart ssh server
/etc/init.d/ssh restart
```
* 5. Generate a ssh-alias(On your pc)
create a file named `~/.ssh/config`, and input below:
```
Host        xxx(alias)
    HostName        216.194.70.6(address)
    Port            22
    User            xxx(username)
    IdentityFile    ~/.ssh/xxx(key)
```
