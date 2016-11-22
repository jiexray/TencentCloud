# Install Anaconda on Tencent Cloud
* 1. Download [anaconda](https://www.continuum.io/downloads)
* 2. Upload anaconda package to TC via scp
```
scp /path/file username@hostname /destination/
```
* 3. Run the install package
```
bash xxx.sh
```
* 4. Put the anaconda2/bin to $PATH
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
* 1. Open ipython notebook without browser
```
ipython notebook --no-browser
```
