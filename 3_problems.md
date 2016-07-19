# 3. Problems
1. **pip安裝套件失敗：**
   1. 改用`easy_install`（須先`apt-get install setuptools`）
   2. 改用`pip --user`，例如`$ pip install --user numpy`
   3. 若先前已安裝過，請使用`--upgrade`，例如`$ sudo pip install numpy --upgrade`

2. **Scipy安裝失敗：**確認以下套件<a href="ref8"><sup>[8]</sup></a>已安裝完成，並reinstall Scipy:
   ```
   $ sudo apt-get install python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose
   $ sudo pip install scipy
   ```


