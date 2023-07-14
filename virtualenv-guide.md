# Creating A Python Virtual Environment

`virtualenv` is a tool for creating isolated Python environments. ([Virtualenv documentation](https://virtualenv.pypa.io/en/stable/))

We use this tool to help manage several dependencies and library versions for different projects. With `virtualenv`, these changes are easily available to other developers without causing conflicts with other Python projects.

This guide contains the steps to install, set up, and test our team's virtual environment on **Windows**.

## Requirements

- [ ] [**Python 3.7 or greater**](https://www.python.org/downloads/windows/). 
	You can check your version on a *Windows command line* with the command `python --version`
- [ ] [**pip**](https://phoenixnap.com/kb/install-pip-windows#ftoc-heading-2) package manager


## Installing `virtualenv`

1.  **On a *Windows command line*, install the** `virtualenv` **module**

    `pip install virtualenv`

2. **Locate your local Python distribution.**
    
    The default path is usually **`C:\%LocalAppData%\Programs\Python\Python39\python.exe`**
    
	>⚠️ If you have trouble finding your distribution, check the [FAQ](#my-python-distribution-is-not-located-at-the-default-path.-how-do-i-find-it).

3.   **Navigate to your project directory with** `cd` **and create a new virtual environment with the path to your Python distribution**
    `virtualenv —python [path to python.exe] venv`
4.  **Activate the newly created virtual environment**
    `.\venv\Scripts\activate`
6.  **Download the latest `requirements.txt` from** github.com/a-velasco/sample-repo **to your project directory**. This file contains the python modules and versions that are used in this virtual environment. It should be regularly checked for updates.
	>⚠️ If you cannot access this repository, check the [FAQ](#how-do-i-get-access-to-the-repository).
7.  **Install packages**
`pip install -r requirements.txt`

The virtual environment is ready to use! **To exit, use the** `deactivate` **command on the same shell.** 

## FAQ
#### My Python distribution is not located at the default path. How do I find it?
You can search for your distribution with Python’s `sys` module. 
Open a *Python shell* and run the commands shown below. The output paths will show the installation directory of your Python distribution.

    >>> import sys
    >>> for p in sys.path: print(p)
    ...
    
    C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\python39.zip
    C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\DLLs
    C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\lib
    C:\Users\MyUsername\AppData\Local\Programs\Python\Python39
    C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\lib\site-packages

 #### I have a Python distribution. Why doesn't my command line recognize it?
First, make sure you are running your *Windows CLI* as administrator.
If this issue persists, it is likely your Python distribution needs to be added to your `PATH` environment variable.
Check out the official [Using Python on Windows](https://docs.python.org/3/using/windows.html) documentation. 

#### How do I know if my modules were installed correctly in the venv?
To see all installed modules, use the command `pip freeze` while `virtualenv` is active. The output will contain the modules present in **`requirements.txt`**, as shown below.

    (venv) C:\Users\MyUsername\Documents\MyProject>pip freeze
    asgiref==3.7.2
    blinker==1.6.2
    click==8.1.4
    colorama==0.4.6
    contourpy==1.1.0
    cycler==0.11.0
    Flask==2.3.2
    ...
    
    (venv) C:\Users\MyUsername\Documents\MyProject>type requirements.txt
    asgiref==3.7.2
    blinker==1.6.2
    click==8.1.4
    colorama==0.4.6
    contourpy==1.1.0
    cycler==0.11.0
    Flask==2.3.2
    ...

 
#### How do I get access to the repository?
If you have a Github account but do not have permission to access the repository, please contact the IT department at 
it@company.com.



