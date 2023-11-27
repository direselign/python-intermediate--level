Virtual Environment
-------------------
A virtual environment in Python is a self-contained directory that encapsulates a specific Python interpreter along with its standard library and site-packages. Virtual environments enable developers to manage project-specific dependencies, avoid version conflicts, and create isolated development environments. The venv module is a built-in tool for creating and managing virtual environments in Python 3.
1. Creating a Virtual Environment:
    - Create a virtual environment using the venv module. Replace myenv with the desired name of your virtual environment.
    ```python -m venv myenv```
    - On Unix or MacOS, you may use python3 instead of python.
2. Activating a Virtual Environment:
    - Activate the virtual environment to use its isolated Python interpreter and libraries.
    - On Windows: `myenv\Scripts\activate`
    - On Unix or MacOS: `source myenv/bin/activate`
    - The command prompt or terminal prompt will change, indicating the active virtual environment.
3) Deactivating a Virtual Environment
    - Deactivate the virtual environment when you're done working on your project. `deactivate`
4)  Installing Packages in a Virtual Environment
    - While the virtual environment is active, use `pip` to install packages.
    ```pip install package_name```
    - Installed packages are specific to the virtual environment.
5)  Freezing and Requirements Files
    - Generate a requirements file to record all installed packages and their versions.
    ```pip freeze > requirements.txt```
    - To install dependencies from a requirements file
    ```pip install -r requirements.txt```
6) Using Different Python Versions
    - Create virtual environments with different Python versions using the --python option.
    ```python -m venv --python=python3.9 myenv```
7) Cloning a Virtual Environment:
    - Clone an existing virtual environment with the --copies option.
    ```python -m venv --copies myenv_clone```