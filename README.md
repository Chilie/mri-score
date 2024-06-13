# mri-score

NOTE: Please run **all** commands from the root directory of the repository, i.e from ``mri-score/``

## Setup environment

1.``python -m venv env``

1.``source env/bin/activate``

1.``pip install -U pip``

1.``pip install -r requirements.txt``

1.``git submodule update --init --recursive``

## Install BART for sensitivity map estimation

BART provides tools for processing MRI data. Our experiments require BART for estimating sensitivity maps, and BART can be installed using the following commands.

1.``sudo apt-get install make gcc libfftw3-dev liblapacke-dev libpng-dev libopenblas-dev``

1.``wget https://github.com/mrirecon/bart/archive/v0.6.00.tar.gz``

1.``tar xzvf v0.6.00.tar.gz``

1.``cd bart-0.6.00``

1.``make``

## Download data and checkpoints

1.``gdown https://drive.google.com/uc?id=1vAIXf8n67yEAPmH2I9qiDWzmq9fGKPYL``

1.``tar -zxvf checkpoint.tar.gz``

1.``gdown https://drive.google.com/uc?id=1mpnV1iXid1PG0RaJswM6t9yI76b2IPxc``

1.``tar -zxvf datasets.tar.gz``

## Script for estimating sensitivity maps from data

The script ``estimate_maps.py`` will estimate sensitivity maps. An example usage is

``python estimate_maps.py --input-dir=datasets/brain_T2 --output-dir=datasets/brain_T2_maps``

## Example commands

We provide configuration files in ``configs/`` that contain hyper-parameters used in our experiments. The experiments can be run using the ``ours.sh``.

## Thanks

The code is based on the [csgm-mri-langevin](https://github.com/utcsilab/csgm-mri-langevin).
