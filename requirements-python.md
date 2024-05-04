<!--
title: 'list-dependences-python.md'
author: 'Elias Albuquerque'
created: '2023-12-20'
update: '2023-12-20'
-->


# Listing Python Project Dependencies

You can generate the `requirements.txt` file and list all the dependencies of 
your project.


- [Using pipreqs:](#using-pipreqs)
- [Using pigar:](#using-pigar)



## Using pipreqs:

You can install the `pipreqs` module with the following command:

```terminal
pip install pipreqs
```

To execute **pipreqs** in the project directory, use the following command:

```terminal
pipreqs /path/to/project/
```

Alternatively, if you’re already in the directory, you can simply use:

```terminal
pipreqs .
```

And if a `requirements.txt` file already exists, you can overwrite it with:

```terminal
pipreqs . --force
```


## Using pigar:

You can install the `pigar` module for generate the requirements file:

```terminal
pip install pigar
```

To execute **pigar**:

```terminal
pigar generate
```
