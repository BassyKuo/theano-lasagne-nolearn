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
安裝python其他套件(scipy requires):[[3]] [scipy]
```
$ sudo apt-get intsall python-matplotlib ipython ipython-notebook python-pandas python-sympy
```
安裝pip installer:
```
$ sudo apt-get install python-pip
```

### Theano安裝[[4]] [theano-install]
```
$ sudo pip install Theano
```

### Lasagne安裝[[5]] [lasagne-install]
```
$ sudo pip intsall lasagne
```

### Nolearn安裝
Nolearn有許多相依套件必須先安裝或版本升級，首先先建立`Requires.txt`:[[6]] [nolearn-doc]
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
最後安裝Nolearn 0.5b1版本:[[7]] [nolearn-0.5b1]
```
$ sudo pip install nolearn==0.5b1
```
---
[scipy]: https://www.scipy.org/install.html
[theano-install]: http://deeplearning.net/software/theano/install_ubuntu.html#install-ubuntu
[lasagne-install]: http://lasagne.readthedocs.io/en/latest/user/installation.html
[nolearn-doc]: http://nolearn.readthedocs.io/en/latest/index.html
[nolearn-0.5b1]: https://jessesw.com/Deep-Learning/

[3] https://www.scipy.org/install.html

[4] [Easy Installation of an Optimized Theano on Current Ubuntu](http://deeplearning.net/software/theano/install_ubuntu.html#install-ubuntu)

[5] http://lasagne.readthedocs.io/en/latest/user/installation.html

[6] http://nolearn.readthedocs.io/en/latest/index.html

[7] [An Introduction to Deep Learning using nolearn](https://jessesw.com/Deep-Learning/)