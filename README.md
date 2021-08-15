Create and upload python package to PyPi 
==========================================


Create a package 
----------------

* Modular code becomes package by adding __init__.py
* The code inside init file gets run when the package is imported
	to python program 
* The package still works if init file is empty but the classes are imported more explicitly 

	``` from prob_distributions_sb.Gaussiandistribution import Gaussian ```

* setup.py is necessary to pip install a package 
* setup file have metadata about package 


Install package locally in a virtual environment 
------------------------------------------------

* Go to the directory where package is stored 
```pip install .```
The . tells pip to look for setup.py 


Upload to Pypi
----------------

* Include license.txt, README and setup.cfg
* Register on [pypi.org](https://pypi.org/) and [test.pypy.org](https://test.pypi.org/)
* Go to the directory where package is stored and execute below

```
python setup.py sdist bdist_wheel
pip install twine 

# commands to upload to the pypi test repository
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
pip install --index-url https://test.pypi.org/simple/ prob-distributions-sb

# command to upload to the pypi repository
twine upload dist/*
pip install prob-distributions-sb
```

```setup.py sdist bdist_wheel```
This command still outputs a folder called dist. The difference is that you will get both a .tar.gz file and a .whl file. The .tar.gz file is called a source archive, whereas the .whl file is a built distribution. The .whl file is a newer type of installation file for Python packages. When you pip install a package, pip firsts look for a .whl file (wheel file); if there isn't one, it looks for the .tar.gz file.

A .tar.gz file (an sdist) contains the files needed to compile and install a Python package. A .whl file (a built distribution) only needs to be copied to the proper place for installation. Behind the scenes, pipinstalling a .whl file has fewer steps than installing a .tar.gz file.










