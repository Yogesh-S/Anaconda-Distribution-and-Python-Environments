# Python-Environments


### Why you need multiple Python environments?
- You have an application (developed by yourself or by someone else) that once worked beautifully. But now you’ve tried to run it, and it is not working. Perhaps one of the packages is no longer compatible with the other parts of your program (due to the so-called breaking changes). A possible solution is to set up a new environment for your application, that contains the Python version and the packages that are completely compatible with your application.
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
After activating enviroment run the following command
```
conda install ipykernel
```
then `Go to Jupyter notebook >> New >> Notebook >> Python (conda env:mynewenv)`

Note: Jupyter Notebook runs in the same environment it was created in irrespective of the environments you choose to open.

To know in which environment Jupyter Notebook executes
```
import sys
print(sys.executable)
```

To deactivate `mynewenv`
```
conda deactivate
```

To remove environment permanently
```
conda env remove -n mynewenv
```

### Other usefull commands
To list out the available environments in a Conda installation
```
conda env list
```
```
>>> # conda environments:
#
base                  *  C:\Program Files\Anaconda3
flappybird               C:\Program Files\Anaconda3\envs\flappybird
mynewenv                 C:\Program Files\Anaconda3\envs\mynewenv
style-transfer           C:\Program Files\Anaconda3\envs\style-transfer
test_latest              C:\Program Files\Anaconda3\envs\test_latest
```
To get the Conda version of the currently active environment,
```
conda --version
```
```
>>> conda 4.10.1
```

To get a detailed list of information about the environment,
```
conda info
```
```
>>>  active environment : base
    active env location : C:\Program Files\Anaconda3
            shell level : 1
       user config file : C:\Users\INYOS1\.condarc
 populated config files : C:\Users\INYOS1\.condarc
          conda version : 4.10.1
    conda-build version : 3.18.8
         python version : 3.7.3.final.0
...
```

To list out all the installed packages in the currently active environment,
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
...
```

To install a package (for instance seaborn)
```
conda install seaborn
```

You can also specify the package’s version:
```
conda install seaborn=0.7.0
```

To update all the installed packages (in the current environment):
```
conda update
```

To update a specific package
```
conda update seaborn
```

To remove the seaborn package
```
conda remove seaborn
```

#### Changing an environment’s Python version
Python is also a package. First, you should list out the available Python versions:
```
conda search -f python
```
```
>>> Loading channels: done
# Name                       Version           Build  Channel
python                        2.7.13     h1b6d89f_16  pkgs/main
python                        2.7.13     h9912b81_15  pkgs/main
python                        2.7.13     hb034564_12  pkgs/main
python                        2.7.14     h2765ee6_18  pkgs/main
...
python                         3.9.1      h6244533_2  pkgs/main
python                         3.9.2      h6244533_0  pkgs/main
python                         3.9.4      h6244533_0  pkgs/main
python                         3.9.5      h6244533_3  pkgs/main
```

To update the Python version to the latest version of its branch
```
conda update python
```

Update to specific python version
```
conda install python=3.9.1
```

#### Adding PIP packages
PIP packages are also installable into Conda environments.
```
pip install lightgbm
```
<br />

For detailed explaination of Python envirnoments and how to manage them with Conda [refer this document](https://www.freecodecamp.org/news/why-you-need-python-environments-and-how-to-manage-them-with-conda-85f155f4353c/).
