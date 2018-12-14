# mgcpy

[![Coverage Status](https://coveralls.io/repos/github/NeuroDataDesign/mgcpy/badge.svg?branch=master)](https://coveralls.io/github/NeuroDataDesign/mgcpy?branch=master)
[![Build Status](https://travis-ci.com/NeuroDataDesign/mgcpy.svg?branch=master)](https://travis-ci.com/NeuroDataDesign/mgcpy)
[![PyPI](https://img.shields.io/pypi/v/mgcpy.svg)](https://pypi.org/project/mgcpy/)
[![PyPI - Downloads](https://img.shields.io/pypi/dm/mgcpy.svg)](https://pypi.org/project/mgcpy/)
[![DockerHub](https://img.shields.io/docker/automated/tpsatish95/mgcpy.svg)](https://hub.docker.com/r/tpsatish95/mgcpy/)
[![DOI](https://zenodo.org/badge/147731955.svg)](https://zenodo.org/badge/latestdoi/147731955)
[![Documentation Status](https://readthedocs.org/projects/mgcpy/badge/?version=latest)](https://mgcpy.readthedocs.io/en/latest/?badge=latest)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![PEP8](https://img.shields.io/badge/code%20style-pep8-orange.svg)](https://www.python.org/dev/peps/pep-0008/)
[![Code Climate](https://api.codeclimate.com/v1/badges/979888a65926b3f27971/maintainability)](https://codeclimate.com/github/NeuroDataDesign/mgcpy/maintainability)

`mgcpy` is a Python package containing tools for multiscale graph correlation and other statistical tests, that is capable of dealing with high dimensional and multivariate data.

**Documentation:** https://mgcpy.readthedocs.io/en/latest/

## Installation Guide:

### Install from PyPi
```
pip3 install mgcpy
```

### Install from Github
```
git clone https://github.com/NeuroDataDesign/mgcpy
cd mgcpy
python3 setup.py install
```
- `sudo`, if required
- `python3 setup.py build_ext --inplace  # for cython`, if you want to test in-place, first execute this

## Setting up the development environment:
- To build image and run from scratch:
  - Install [docker](https://docs.docker.com/install/)
  - Build the docker image, `docker build -t mgcpy:latest .`
    - This takes 10-15 mins to build
  - Launch the container to go into mgcpy's dev env, `docker run -it --rm --name mgcpy-env mgcpy:latest`
- Pull image from Dockerhub and run:
  - `docker pull tpsatish95/mgcpy:latest` or `docker pull tpsatish95/mgcpy:development`
  - `docker run -it --rm -p 8888:8888 --name mgcpy-env tpsatish95/mgcpy:latest`


- To run demo notebooks (from within Docker):
  - `cd demos`
  - `jupyter notebook --ip 0.0.0.0 --no-browser --allow-root`
  - Then copy the url it generates, it looks something like this: `http://(0de284ecf0cd or 127.0.0.1):8888/?token=e5a2541812d85e20026b1d04983dc8380055f2d16c28a6ad`
  - Edit this: `(0de284ecf0cd or 127.0.0.1)` to: `127.0.0.1`, in the above link and open it in your browser
  - Then open `mgc.ipynb`

- To mount/load local files into docker container:
  - Do `docker run -it --rm -v <local_dir_path>:/root/workspace/ -p 8888:8888 --name mgcpy-env tpsatish95/mgcpy:latest`, replace `<local_dir_path>` with your local dir path.
  - Do `cd ../workspace` when you are inside the container to view the mounted files. The **mgcpy** package code will be in `/root/code` directory.


## MGC Algorithm's Flow
![MGCPY Flow](https://raw.githubusercontent.com/NeuroDataDesign/mgcpy/master/MGCPY.png)

## Power Curves
- Recreated Figure 2 in https://arxiv.org/abs/1609.05148, with the addition of MDMR and Fast MGC
![Power Curves](https://raw.githubusercontent.com/NeuroDataDesign/mgcpy/master/power_curves_dimensions.png)

## License

This project is covered under the **Apache 2.0 License**.
