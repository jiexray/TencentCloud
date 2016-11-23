# Problem Log
* 1. When import `matplot.pyplot`, and output `ImportError: libSM.so.6: cannot open shared object file: No such file or directory`
Solution:
```
sudo apt-get install libsm6 libxrender1 libfontconfig1
```
