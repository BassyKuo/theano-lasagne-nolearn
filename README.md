# 0. Quick cheatsheet

執行此script以安裝theano, lasagne, nolearn:
(測試安裝環境：**64-bit Ubuntu 14.04**)
```bash
#!/bin/bash
# Easy installation on Ubuntu 14.04 server

### Requirements ###
sudo apt-get update
sudo apt-get install -y python-numpy
if [ $? -eq 100 ]; then 
  sudo mv /var/cache/apt/archives/lock /var/cache/apt/archives/lock_bak
  sudo apt-get install -y python-numpy
fi
sudo apt-get install -y cython python-matplotlib ipython ipython-notebook python-pandas python-sympy python-scipy python-dev python-pip python-nose g++ libopenblas-dev git libblas-dev liblapack-dev libatlas-base-dev gfortran 

### Install Theano, Lasagne, Nolearn ###
# If you want to install local packages, please use `virtualenv` or use `pip install --user`
sudo pip install -r https://raw.githubusercontent.com/dnouri/nolearn/master/requirements.txt
sudo pip install nolearn==0.5b1
```
預設是使用CPU執行，若要使用GPU，請新增`~/.theanorc`:<a href="#ref1">[1]</a>
```
[global]
mode=FAST_RUN
device=gpu
floatX=float32
```
確認是否有設定成功，可執行`check_gpu.py`: [[2]] [ref2]
```python
# Filename: check_gpu.py
from theano import function, config, shared, sandbox
import theano.tensor as T
import numpy
import time

vlen = 10 * 30 * 768  # 10 x #cores x # threads per core
iters = 1000

rng = numpy.random.RandomState(22)
x = shared(numpy.asarray(rng.rand(vlen), config.floatX))
f = function([], T.exp(x))
print(f.maker.fgraph.toposort())
t0 = time.time()
for i in range(iters):
    r = f()
t1 = time.time()
print("Looping %d times took %f seconds" % (iters, t1 - t0))
print("Result is %s" % (r,))
if numpy.any([isinstance(x.op, T.Elemwise) for x in f.maker.fgraph.toposort()]):
    print('Used the cpu')
else:
    print('Used the gpu')
```
---
[ref2]: .#ref2

<a name="ref1">[1]</a> 
http://deeplearning.net/software/theano/library/config.html#config.device

<a name="ref2">[2]</a>
http://deeplearning.net/software/theano/tutorial/using_gpu.html#testing-theano-with-gpu