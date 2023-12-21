<!--
title: 'list-dependences-python.md'
author: 'Elias Albuquerque'
created: '2023-12-20'
update: '2023-12-20'
-->


# Listing Python Project Dependencies

You can generate the `requirements.txt` file and list all the dependencies of 
your project using the `pipreqs` module.


## Installing the pipreqs module:

You can install the `pipreqs` module with the following command:

```python
pip install pipreqs
```


## Running pipreqs module in the project directory:

To execute `pipreqs` in the project directory, use the following command:

```python
pipreqs /path/to/project/
```

Alternatively, if you’re already in the directory, you can simply use:

```python
pipreqs .
```

And if a `requirements.txt` file already exists, you can overwrite it with:

```python
pipreqs . --force
```

This module traverses the project directory and lists all the modules used in 
the application, eliminating the need to create virtual environments. This way, 
you can use the global environment for the installation of external modules.