*If you are the rest users, read the item from 2-4(under title `Install Anaconda on Tencent Cloud for all users`)*

# Install Anaconda on Tencent Cloud for One User
* 1. Download [anaconda](https://www.continuum.io/downloads)
* 2. Upload anaconda package to TC via scp
```
scp /path/file username@hostname /destination/
```
* 3. Run the install package
```
bash xxx.sh
```
* 4. Append the `anaconda2/bin` to `$PATH`
```
export PATH=/home/jiexray/anaconda2/bin:$PATH
```
* 5. Restart/relogin your account, and run command 'ipython'
```
Python 2.7.11 |Anaconda 4.0.0 (64-bit)| (default, Dec  6 2015, 18:08:32)
Type "copyright", "credits" or "license" for more information.

IPython 4.1.2 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.
```
*Good*

## Tips:
* 1. Open jupyter notebook without browser
```
ipython notebook --no-browser
```

# Install Anaconda on Tencent Cloud for All Users
* 1. Let the installer put the folder in a common place(/opt)
```
Install path: /opt/anaconda2
```
* 2. Append the /opt/anaconda2/bin to `$PATH`
```
vi .bashrc
```
Append this at the bottom of the file:
```
export PATH=/opt/anaconda2/bin:$PATH
```
* 3. Relog and try command `ipython`.
```
Python 2.7.11 |Anaconda 4.0.0 (64-bit)| (default, Dec  6 2015, 18:08:32)
Type "copyright", "credits" or "license" for more information.

IPython 4.1.2 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.
```
* 4. For more information about [jupyter notebook](https://github.com/jiexray/TencentCloud/blob/master/remote-connect-jupyter-notebook.md)
