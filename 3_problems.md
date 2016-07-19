# 3. Problems
1. **使用pip安裝套件失敗：**
   1. 改用`easy_install`（須先`apt-get install setuptools`）
   2. 改用`pip --user`，例如`$ pip install --user numpy`（安裝套件須有sudoer的身分，透過`--user`可以安裝在自己$HOME底下不需要sudo）
   3. 若套件先前已安裝過，請使用`--upgrade`，例如`$ sudo pip install numpy --upgrade`

2. **Scipy安裝失敗：**確認以下套件<a href="ref8"><sup style="font-size:12px;">[8]</sup></a>已安裝完成，並reinstall Scipy:
   ```
   $ sudo apt-get install python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose
   $ sudo pip install scipy
   ```
   若有卡住的情形出現，不是失敗，只是要等很久的時間才會成功；若還是沒有進度的話可考慮安裝其他版本，例如：
   ```
   $ pip install scipy==0.10.1
   ```
3. **安裝時顯示"Could not find a tag or branch '8f4f9b2'"：**系統會自動安裝相近的版本，例如：**Lasagne 0.2.dev1**.


---
<sup id="ref8">[8]</sup> https://www.scipy.org/install.html