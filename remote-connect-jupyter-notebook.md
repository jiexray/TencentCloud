# Remote Connect to Jupyter Notebook on TC
* 1. Log in TC, generate juptyer notebook `config` file
```
jupyter notebook --generate-config
```
* 2. Open a ipython window, and generate a key.
```
In [1]: from notebook.auth import passwd
In [2]: passwd()
Enter password: 
Verify password: 
Out[2]: 'sha1:ce23d945972f:34769685a7ccd3d08c84a18c63968a41f1140274'
```
Copy the 'sha1:...' key
* 3. Modify jupyter nootbook `config` file
```
vim ~/.jupyter/jupyter_notebook_config.py
```
Add content below: 
```
c.NotebookApp.ip='*'
c.NotebookApp.password = u'sha:ce...present key'
c.NotebookApp.open_browser = False
c.NotebookApp.port =8888 #arbitrary port
```
* 4. Start jupyter notebook
```
jupyter notebook
```
* 5. Remote connect to jupyter notebook with local browser `http://address_of_remote:8888`
* 6. If failed for firewall. Build a SSH tunnel
```
ssh username@address_of_remote -L127.0.0.1:1234:127.0.0.1:8888
```
You can visit `localhost:1234` to access to jupyter
