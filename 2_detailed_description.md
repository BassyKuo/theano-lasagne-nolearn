# 2. Detailed description

### 環境安裝
安裝python, python-dev, Numpy, Scipy, Nose, g++, git:
```
$ sudo apt-get python python-numpy python-scipy python-dev python-nose g++ git
```
安裝BLAS/LAPACK環境:
```
$ sudo apt-get install libopenblas-dev libblas-dev liblapack-dev libatlas-base-dev gfortran
```
安裝python其他套件(scipy requires):<a href="#ref3"><sup style="font-size:12px;">[3]</sup></a>
```
$ sudo apt-get intsall python-matplotlib ipython ipython-notebook python-pandas python-sympy
```
安裝pip installer:
```
$ sudo apt-get install python-pip
```

### Theano安裝<a href="#ref4"><sup style="font-size:12px;">[4]</sup></a>
```
$ sudo pip install theano
```

### Lasagne安裝<a href="#ref5"><sup style="font-size:12px;">[5]</sup></a>
```
$ sudo pip intsall lasagne
```

### Nolearn安裝
Nolearn有許多相依套件必須先安裝或版本升級，首先先建立`Requires.txt`:<a href="#ref6"><sup style="font-size:12px;">[6]</sup></a>
```bash
numpy==1.10.4
scipy==0.16.1
Theano==0.8
Lasagne==0.2.dev1
joblib==0.9.3
scikit-learn==0.17
tabulate==0.7.5
```
透過pip安裝:
```
$ sudo pip install -r Requires.txt
```
最後安裝Nolearn 0.7版本<a href="#ref7"><sup style="font-size:12px;">[7]</sup></a>:
```
$ sudo pip install git+https://github.com/dnouri/nolearn.git@master#egg=nolearn==0.7.git
```
### 測試
可在python環境下import packages，若無出現error即為安裝成功:
```
$ python
>>> import numpy
>>> import scipy
>>> import theano
>>> import lasagne
>>> import nolearn
>>> 
```
也可利用`pip show`顯示版本資訊，例如:
```
$ pip show theano
---
Name: Theano
Version: 0.8.0
Location: /home/bass/.local/lib/python2.7/site-packages
Requires: numpy, scipy, six

```

---
[scipy]: https://www.scipy.org/install.html
[theano-install]: http://deeplearning.net/software/theano/install_ubuntu.html#install-ubuntu
[lasagne-install]: http://lasagne.readthedocs.io/en/latest/user/installation.html
[nolearn-doc]: http://nolearn.readthedocs.io/en/latest/index.html
[nolearn-0.5b1]: https://jessesw.com/Deep-Learning/

<sup id="ref3">[3]</sup> https://www.scipy.org/install.html

<sup id='ref4'>[4]</sup> [Easy Installation of an Optimized Theano on Current Ubuntu](http://deeplearning.net/software/theano/install_ubuntu.html#install-ubuntu)

<sup id='ref5'>[5]</sup> http://lasagne.readthedocs.io/en/latest/user/installation.html

<sup id='ref6'>[6]</sup> http://nolearn.readthedocs.io/en/latest/index.html

<sup id='ref7'>[7]</sup> https://pythonhosted.org/nolearn/