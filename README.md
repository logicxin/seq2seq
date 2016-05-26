# Seq2Seq for summarization in torch 7

The code is a simple implement of the popular deep learning model --- `seq2seq`. Here we use python to process the dataset, because it's more efficient than Torch, and the other codes are all written by Torch. 

# File

- `preprocessing.py` is used for processing the [LCSTS](http://icrc.hitsz.edu.cn/Article/show/139.html) dataset, which aims to solve Chinese short text summarization task. Because of the large size and the copyright, we don't publish it here. If you are interested in it, you can send an application form to get. Also, you can use other datasets instead if you are glad to.

You must process dataset before you run the training code,

<code>python preprocessing.py</code>


- `Summarization.lua` is a wrapper file which contains `Dataset` class and `Seq2Seq` class.

- `Dataset.lua` is a class to achieve data from hdf5 file processed by python.

- `Seq2Seq.lua` is a class to build seq2seq model.

- `Train.lua` contains all the training processes.

You can run `th Train.lua` directly to train seq2seq model.

If you want to use GPU, you can run:

<code>th Train.lua --opencl</code>  or

<code>th Train.lua --cuda</code>

# Installing

Before running code, you need to ensure the packages below installed:
 
- `hdf5`, a file format connect python and torch

For python, <code>pip install h5py</code>,

For torch, <code>luarocks install hdf5</code>

- `jieba`, a popular Chinese Tokenizer

For python, <code>pip install jieba</code>

- `rnn`, a rnn package for RNN model, like LSTM, GRU etc.

For torch , <code>luarocks install rnn</code>

If you need to use cuda or opencl, please install packages below:

- opencl

<code>luarocks install cltorch</code>

<code>luarocks install clnn</code>

- cuda

<code>luarocks install cutorch</code>

<code>luarocks install cunn</code>

# Future works

- `Beam Search`, to generate a more excellent summarzation.

- `Attention Model`, to implement a soft attention layer in model part.













 

