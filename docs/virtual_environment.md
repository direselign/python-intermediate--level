Virtual Environment
-------------------
A Python environment refers to the combination of tools, libraries, 
and settings that allow you to develop, run, and manage Python applications. 
Managing environments is crucial to avoid conflicts between different projects and 
to ensure that dependencies are consistent. 
Here are some aspects of Python environments:

## Virtual Environments:
- Description: Virtual environments allow you to create isolated Python environments for your projects. Each environment can have its own set of dependencies without interfering with other projects.
- Tools: venv (built-in), virtualenv, conda (for data science projects).
Example:
```
# Create a virtual environment
python -m venv name-of-enviroment(ex. myenv)

# Activate the virtual environment
source myenv/bin/activate  # On Unix or MacOS
myenv\Scripts\activate  # On Windows
```
## Package Management:
- Description: Tools to manage Python packages, install dependencies, and ensure version consistency.
- Tools: pip (default Python package installer), conda (especially for data science packages).
Examples:
```
# Install a package
pip install package_name

# Install from requirements file
pip install -r requirements.txt

# Conda example
conda install package_name
```
## Requirements Files:
- Description: A file listing all the dependencies and their versions required for a project.
- Example:
```
# requirements.txt
Flask==2.0.1
requests>=2.25.1
```