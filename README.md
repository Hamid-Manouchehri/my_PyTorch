# my_PyTorch
notes on PyTorch crash course: https://www.youtube.com/watch?v=V_xro1bcAuA&amp;t=24874s


## Conda env:
### Initial creating of a conda env:
1. Updating the <u>list</u> of available ubuntu packages (OS-level)
```
sudo apt update
```

2. Creating the conda env for Deep Learning (PyTorch):
```
conda create -n dl_env python=3.10
```

3. Activating the package:
```
conda activate dl_env
```

4. Add conda-forge channel/repository:
```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

5. Installing required python packages - prefer conda-forge; only use pip when necessary.:
```
conda install numpy scipy pandas matplotlib jupyterlab ...
```

6. Making the env reproducible:
```
conda env export --no-builds > environment.yml
```

Note: Never use `sudo` for installing packages inside conda env, that installs into system Python and can shadow/override conda wheel.

### Recreating the conda package on another machine:

Creating the conda env and installing all the python packages:
```
conda env create -f environment.yml
```
Make sure you update the conda env after installing any further packages:
```
conda update --all
```