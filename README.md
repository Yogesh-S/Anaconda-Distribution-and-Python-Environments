# Python-Environments


### Why you need multiple Python environments?
- You have an application (developed by yourself or by someone else) that once worked beautifully. But now you’ve tried to run it, and it is not working. Perhaps one of the packages is no longer compatible with the other parts of your program (due to the so-called breaking changes). A possible solution is to set up a new environment for you application, that contains the Python version and the packages that are completely compatible with your application.
- You are collaborating with someone else, and you want to make sure that your application is working on your team member’s computer, and vice versa, so you can also set up an environment for your co-worker’s application(s).

### Package and environment managers
- **PIP** (a Python package manager; funnily enough, it stands for “Pip Installs Packages”) with virtualenv (a tool for creating isolated environments)
- **Conda** (a package and environment manager)

### Why conda is better than PIP?
- Clear Structure: It is easy to understand its directory structure
- Transparent File Management: It doesn’t install files outside its directory
- Flexibility: It contains a lot of packages (PIP packages are also installable into Conda environments)
- Multipurpose: It is not only for managing Python environments and packages — you can also use it for R (a programming language for statistical computing)

### Python environments: root and additional
The process looks like this: the installer installs **Conda** first. Then, Conda creates a **root environment** that contains two things:
- a certain version of Python and
- some basic packages.

Next to the root environment, you can create as many **additional environments** as you want. And the whole point is that these additional environments can contain different versions of Pythons and other packages.

### Directory structure
Conda system is installed into a single directory usually the path is: `C:\Program Files\Anaconda3`. It contains the root environment and two important directories:

- `\pkgs` (it contains the cached packages in compressed and uncompressed formats)
- `\envs` (it contains the environments — except for the root environment — in separate subdirectories)

### Managing environments

Execute the following commands in Anaconda Promt to create/manage python environments:
#### 1. Creating New Environment
```
conda create --name mynewenv python=3.7
```
#### 2. Activating an Environment
Inside a new Conda installation, the root environment is activated by default, and the command promt appears with this path

`>>> (base) C:\WINDOWS\system32>`

Use the following command to activate `mynewenv`
```
activate mynewenv
```

`(mynewenv) C:\WINDOWS\system32>`

#### 3. Switching environments in Jupyter Notebook
To switch kernels in Jupyter Notebook
```
conda install ipykernel
```
After running the above code Go to Jupyter notebook >> New >> Notebook >> Python (conda env:mynewenv)

Note: Jupyter Notebook runs in the same environment it was created in irrespective of the environments you choose to open with.

To know which env the notebook is running in run the following in Notebook
```
import sys
print(sys.executable)
```

To deactivate `mynewenv`
```
conda deactivate
```


```
conda list
```
```
>>> # packages in environment at C:\Program Files\Anaconda3:
#
# Name                    Version                   Build  Channel
_ipyw_jlab_nb_ext_conf    0.1.0                    py37_0
_tflow_select             2.3.0                       mkl
absl-py                   0.8.1                    pypi_0    pypi
alabaster                 0.7.12                   py37_0
anaconda-client           1.8.0            py37haa95532_0
anaconda-navigator        1.9.7                    py37_0
anaconda-project          0.10.0             pyhd3eb1b0_0
```
